# MIT-HAN-LAB-Flux-Examples

mithanlab-flux-quantized.ipynb is where I actually load and test the model in the configured environment with the precompiled cuda code.
Notes: 
-There were speed improvements, 25 seconds to ~19 seconds (underwhelming as I was expecting 3-10x improvement, but I may have done something incorrectly)
-Memory improvements, from 31 gb allocated during inference to 9gb during inference (a welcome improvement, because I can now use less expensive gpus in cloud-compute) - The notebook will say 19 gb but this is because i had another model in memory at that time
-I tried to use a secondary method called para-attention for dynamic caching of residual outputs, however, no improvement gained (expected).

deepcompressorcompilation.ipynb is where I compiled the whl file for the nunchaku library, I ran this on google colab with only 2 threads, you can increase that number if you compile on a better system. I have only compiled this for sm_80 systems compatible with A100 GPUs. In the future I can release whls for NVIDIA GPUs with architectures sm_86 (Ampere: RTX 3090, A6000) and sm_89 (Ada: RTX 4090), just create an issue, or compile it yourself and I can see about adding your whl in a pull request 

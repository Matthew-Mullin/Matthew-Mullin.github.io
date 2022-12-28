---
title: How to properly install CUDA on Ubuntu Linux (NVCC)
date: 2022-10-12 12:00:00 -500
categories: [tutorial,software]
tags: [cuda,linux,install,software]
---
# Install

1. Follow this: https://developer.nvidia.com/cuda-downloads
2. Reboot computer
3. Open a terminal and run `nvidia-smi` as a check
4. Run the following in the terminal (source: https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html):

```bash
nano /home/username/.bashrc
```
write the following 2 lines in the bashrc file:
```bash
export PATH=/usr/local/cuda/bin${PATH:+:${PATH}}$
export LD_LIBRARY_PATH=/usr/local/cuda/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
```
5. open up a new terminal window and do `nvcc –version` to check if everything is working

If you want to work with .cu scripts in vscode, install nsight extension (only extension made by Nvidia)

Guide for trouble shooting: https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html
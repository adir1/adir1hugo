---
title: nVidia CUDA and the Future of Computing
description: nVidia interesting history and amazing future potential, that must be made more approachable
author: Adi Rabinovich
type: post
heroStyle: "background"
showTableOfContents: true
draft: true
date: 2024-08-28T11:11:11+00:00
url: /2024/nvidia-cuda-future-computing/
tags:
  - nVidia
  - CUDA
  - GPU
  - AI
  - Open-Source
  - Python

---
## TLDR

Discuss quick history of nVidia and what is CUDA, and then dive a bit into dependencies mess, versioning mess - and then specifically discuss the LD_LIBRARY_PATH fiasco. Since there are so many tools installed on machine, and there is already pip which has standards?!

pip install nvidia-cublas-cu12 nvidia-cudnn-cu12

export LD_LIBRARY_PATH=`python3 -c 'import os; import nvidia.cublas.lib; import nvidia.cudnn.lib; print(os.path.dirname(nvidia.cublas.lib.__file__) + ":" + os.path.dirname(nvidia.cudnn.lib.__file__))'`


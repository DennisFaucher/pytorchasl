# Recognizing American Sign Language with PyTorch
![ASL Video Frame](https://github.com/DennisFaucher/pytorchasl/blob/master/images/ASL%20Recognition.png)

## Why
NVIDIA had recently written up [instructions](https://github.com/dusty-nv/jetson-inference/blob/master/docs/pytorch-collect.md) on how to train models on the Jetson Nano rather than in DIGITS on x86. Also, my daughter is President of the ASL club at her school.

## Quick Demo Video
Demo Video: https://youtu.be/z7-9uf8hzfg

## Requirements
* NVIDIA Jetson [Nano](https://developer.nvidia.com/embedded/jetson-nano-developer-kit) or [Xavier](https://developer.nvidia.com/embedded/jetson-agx-xavier-developer-kit)
* NVIDIA [JetPack OS](https://developer.nvidia.com/embedded/jetpack)
* ASL [Images](https://github.com/loicmarie/sign-language-alphabet-recognizer) for Training
* NVIDIA PyTorch Training [Instructions](https://github.com/dusty-nv/jetson-inference/blob/master/docs/pytorch-collect.md)

## How
### Install JetPack on your Jetson Nano or Xavier
Follow the instructions on the JetPack page above
### Clone a Copy of the ASL Training images
````[bash]
git clone https://github.com/loicmarie/sign-language-alphabet-recognizer.git
````
### Clone a Copy of the NVIDIA Jetson-Inference Code Including PyTorch
````[bash]
git clone https://github.com/dusty-nv/jetson-inference.git
````
(You should really read the entire ReadMe and build all the machine learning tools from source, but for this project, we just need to clone the repository.)
### Split the ASL Data into Train, Test, & Val Folders
Use my [split.py](https://github.com/DennisFaucher/pytorchasl/blob/master/split.py) script for this. Just change line 7 to the parent directory of all the ASL data on your computer.
### Create a labels.txt File
Or just use [mine](https://github.com/DennisFaucher/pytorchasl/blob/master/labels.txt)
## Thank You


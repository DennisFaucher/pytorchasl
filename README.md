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
$ git clone https://github.com/loicmarie/sign-language-alphabet-recognizer.git
````
### Clone a Copy of the NVIDIA Jetson-Inference Code Including PyTorch
````[bash]
$ git clone https://github.com/dusty-nv/jetson-inference.git
````
(You should really read the entire ReadMe and build all the machine learning tools from source, but for this project, we just need to clone the repository.)
### Split the ASL Data into Train, Test, & Val Folders
Use my [split.py](https://github.com/DennisFaucher/pytorchasl/blob/master/split.py) script for this. Just change line 7 to the parent directory of all the ASL data on your computer.
### Create a labels.txt File
Or just use [mine](https://github.com/DennisFaucher/pytorchasl/blob/master/labels.txt)
### Create a Model Directory
````[bash]
$ mkdir asl_model
````
### Start Training Your Model
````[bash]
$ cd jetson-inference/python/training/classification
$ python3 train.py --model-dir=<PATH-TO-YOUR-MODEL-DIR> <PATH-TO-YOUR-DATASET>

(The training will run for 35 epochs as a default. After each epoch you should see the accuracy at 
1(00%) confidence and at 5(0%) confidence increase.)

Epoch: [0] completed, elapsed time 1016.668 seconds (16 minutes. 16*30=480/60=8 hours. 11 AM - 7 PM.
Test: [1670/1679]	Time  0.038 ( 0.035)	Loss 9.4062e-03 (8.0129e-01)	Acc@1 100.00 ( 73.59)	Acc@5 100.00 ( 96.40)
 * Acc@1 73.716 Acc@5 96.418
saved best model to:  ./asl_model/model_best.pth.tar

````
### Convert Your Tensorflow Model to an ONNX Model
````[bash]
$ python3 onnx_export.py --model-dir=<PATH-TO-YOUR-MODEL-DIR>
model exported to:  ./asl_model/resnet18.onnx
````

### Test Your Model
Since I am lousy at ASL, I created a video of all the validation images as input to the NVIDIA compiled imagenet program from jetson-inference. You will need to build everything in jetson-inference first using these [instructions](https://github.com/dusty-nv/jetson-inference/blob/master/docs/building-repo-2.md) 
````[bash]
$ sudo apt-get update
$ sudo apt-get install git cmake libpython3-dev python3-numpy
$ git clone --recursive https://github.com/dusty-nv/jetson-inference
$ cd jetson-inference
$ mkdir build
$ cd build
$ cmake ../
$ make -j$(nproc)
$ sudo make install
$ sudo ldconfig
````
Once everything in jetson-inference is built, you can use the compiled imagenet program to test your model against my [input video](https://github.com/DennisFaucher/pytorchasl/blob/master/asl_val.avi).
## Thank You


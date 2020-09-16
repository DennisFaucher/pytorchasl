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
### Pull a Copy of the ASL Trianing images
````[bash]
git clone https://github.com/loicmarie/sign-language-alphabet-recognizer.git
````

## Thank You
VMware installation. I used VMware Parallels, but vSphere could just as easily be used.
IFTTT
DropBox
Keyboard Maestro for Mac (www.keyboardmaestro.com)
How
Connect IFTTT to Google Assistant and DropBox
Follow the instructions at these links: https://ifttt.com/google_assistant & https://ifttt.com/dropbox

Create Google Assistant Skill in IFFTT
I created 4 Applets in IFTTT - Clone, Start, Stop, Enter. They are all pretty identical

Click Explore and the click + to create a new applet

You will see "If + This Then That"

Click on "+ This"

Search for "assistant" and then click Google Assitant

Click "Say a phrase with a text ingredient"

This is how I filled out my Google Assitant step for the Clone VM applet.

Google Step

Click "Create Trigger"

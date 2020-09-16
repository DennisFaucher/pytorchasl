# Teaching Jetson Nano to Recognize American Sign Language with PyTorch

## Why
NVIDIA had recently written up [instructions](https://github.com/dusty-nv/jetson-inference/blob/master/docs/pytorch-collect.md) on how to train models on the Nano rather than in DIGITS on x86. Also, my daughter is President of the ASL club at her school.

## Quick Demo Video
Demo Video: https://youtu.be/enyho_JCdhg

## Requirements
Google Home
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

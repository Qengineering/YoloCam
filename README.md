# YoloCam
![output image]( https://qengineering.eu/images/YoloCamAdGitAd.webp )
## AI camera with live feed, email notification, Gdrive storage and event triggered GPIO.<br>
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)<br/><br/>

## Introduction.
YoloCam is a software package running on a Raspberry Pi 4, 3 or Zero 2 W.<br>
It transforms the Rpi into a stand-alone AI-powered camera.<br>
With a deep learning model, it detects objects in the camera scene.<br><br>
You can define what YoloCam does when it recognizes an object.<br>
For instance, send you a mail. Or make a movie and store it at Gdrive. Or activate one of its GPIO pins.<br>
At the same time, you can view your footage in any browser.<br><br>
Installation is simple. Just download the software and flash it to an SD card.<br>
Once inserted into your Raspberry Pi, everything works right away.<br>
The software comes with the latest Raspberry Pi Bullseye operating system.<br>
You don't need to be able to program. However, the used C++ source code is available the image.<br><br>
Given the many hours of work, we ask you for a small one-time fee for the license.<br>
See our [shop](https://qengineering.eu/shop.html) where we explain how the license works.<br><br> 
![output image]( https://qengineering.eu/images/YoloCamAdGitScreen.webp )
> A red box is a recognized moving object. Blue boxes are recognized stationary objects.

------------

## Hardware.
To get the YoloCam working, you need the following hardware:
- A Raspberry Pi 4, 3B+ or Zero 2W.
- A cheap RPi V1 camera ([$ 6,62](https://www.reichelt.nl/nl/nl/raspberry-pi-camera-5mp-v1-3-rpi-cam-5mp-p314570.html?&trstct=pos_6&nbc=1)), as the deep learning model only work with small image sizes.
- An SD-card (min 16 GB) holding all the software.

------------

## Software.
There are two versions of the YoloCam software. You have to choose which one you want to use.<br><br>
The _**GPIO**_ version. This version activates the GPIO output pins when a recognized object triggers an event.<br>
There is no live feed to your browser. You can only watch the video on your monitor. Or via VNC, of course.<br>
The GPIO outputs acts in real time. There is no 10-second latency.<br><br>
The _**email**_ version. This version sends emails and records movies when a recognized object triggers an event.<br>
There is a live feed to your browser. It has a latency of 10 seconds due to the HLS streaming, because it takes some time to collect all the information from the stream, get the individual packets and 'glue' them into one video stream.<br>
By the way, thanks to this latency, you will receive your emails 5 seconds before the actual movement is visible in your browser so you can log in.
#### Tip.<br>
Start with the email version if this is your first time using YoloCam. You get a lot of inside information on how everything works, with a detailed email to help you tune your events. And for the price, you can't beat it.
![output image]( https://qengineering.eu/images/EmailExampleYoloCam2.png )

------------

## Downloading.
Select the desired version from the matrix below.

| Model  | email | GPIO |
| ------------- | :-----:  | :-----:  |
| Raspberry Pi 4 | [image](https://ln5.sync.com/dl/38b35f330/sp4pcp3z-pktpgbn5-uku9w245-5gm6zze8) | soon |
| Raspberry Pi 3B+ | [image](https://ln5.sync.com/dl/51b691c20/4gb8n8pc-kqdr2529-szkaav4m-nx3jcchm) | soon |
| Raspberry Pi Zero 2W | [image](https://ln5.sync.com/dl/61432a2d0/ukhr6gne-q9kyvsks-zb45yrmx-mxiu7pdx)  | soon |

Once the file has been downloaded, you need to flash it to an SD card. Use a good quality SD with a minimum size of 16 GByte for this.<br>
On the [Raspberry Pi website](https://www.raspberrypi.com/documentation/computers/getting-started.html), you can follow the instructions on how to flash an image.<br>
Obvious, don't select a standard OS, but the file you just downloaded. For instance' `YoloCam_Rpi4_email.xz`.<br><br>
![output image]( https://qengineering.eu/images/FlashShopRpi.webp )<br><br>
Instead of the `Raspberry Pi Imager`, some people prefer `balenaEtcher`. It doesn't matter, they all do it perfectly.

------------

## Tip.

We used the cheap RPi camera V1 for € 6,66. It works fine. However, the tiny plug from the embedded sensor to the PCB often can be loose. Somehow the software still supported the camera but didn't receive any video anymore. It took quite a while before we discovered the cause; the connector. Once glued, it now functions perfectly.<br/><br/>
![output image]( https://qengineering.eu/images/CheapRPiCam.webp)

------------

## Dependencies.
To run the application, you have to:
- A raspberry Pi 4 with a 32 or 64-bit operating system. It can be the Raspberry 64-bit OS, or Ubuntu 18.04 / 20.04. [Install 64-bit OS](https://qengineering.eu/install-raspberry-64-os.html) <br/>
- The Tencent ncnn framework installed. [Install ncnn](https://qengineering.eu/install-ncnn-on-raspberry-pi-4.html) <br/>
- OpenCV 64 bit installed. [Install OpenCV 4.5](https://qengineering.eu/install-opencv-4.5-on-raspberry-64-os.html) <br/>
- Code::Blocks installed. (```$ sudo apt-get install codeblocks```)

------------

## Installing the app.
To extract and run the network in Code::Blocks <br/>
$ mkdir *MyDir* <br/>
$ cd *MyDir* <br/>
$ wget https://github.com/Qengineering/YoloV4-ncnn-Raspberry-Pi-4/archive/refs/heads/master.zip <br/>
$ unzip -j master.zip <br/>
Remove master.zip, LICENSE and README.md as they are no longer needed. <br/> 
$ rm master.zip <br/>
$ rm LICENSE <br/>
$ rm README.md <br/> <br/>
Your *MyDir* folder must now look like this: <br/> 
parking.jpg <br/>
busstop.jpg <br/>
YoloV4.cpb <br/>
yoloV4.cpp <br/>
yolov4-tiny-opt.bin <br/>
yolov4-tiny-opt.param <br/><br/>
If you want to run the full YoloV4 version you need: <br/>
yolov4.bin (download this 245 MB file from [Mega](https://mega.nz/file/Vsg02bJK#2h0QAd8ZUEykb6hi-yOcIAZKXnCBY0mevz8xkHYCmMM))<br/>
yolov4.param <br/><br/>

------------

## Running the app.
To run the application load the project file YoloV4.cbp in Code::Blocks. More info or<br/> 
if you want to connect a camera to the app, follow the instructions at [Hands-On](https://qengineering.eu/deep-learning-examples-on-raspberry-32-64-os.html#HandsOn).<br/><br/>

![output image]( https://qengineering.eu/images/test_busV4.jpg )


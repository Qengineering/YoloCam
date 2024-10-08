# YoloCam
![output image]( https://qengineering.eu/images/YoloCamAdGitAd.webp )
## AI camera with live feed, email notification, Gdrive storage and event-triggered GPIO/URL.<br>
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)<br/><br/>

## Introduction.
YoloCam is a software package running on a Raspberry Pi 4, 3 or Zero 2 W.<br>
It transforms the Rpi into a stand-alone AI-powered camera.<br>
With a deep learning model, it detects objects in the camera scene.<br><br>
You can define what actions YoloCam performs when it recognizes an object.<br>
For instance, send you an email. Or make a movie and store it at Gdrive. Or activate one of its GPIO pins.<br>
At the same time, you can view your footage in any browser.<br><br>
Installation is simple. Just download the software and flash it to an SD card.<br>
Once inserted into your Raspberry Pi, everything works right away.<br>
The software comes with the latest Raspberry Pi Bullseye operating system.<br>
You don't need to be able to program. However, the used C++ source code is available on the image.<br><br>
Given the many hours of work, we ask you for a small one-time fee for the license (€ 10,00).<br>
See our [shop](https://qengineering.eu/shop.html) where we explain how the license works.<br><br> 
![output image]( https://qengineering.eu/images/YoloCamAdGitScreen.webp )
> A red box is a recognized moving object. Blue boxes are recognized stationary objects.

------------

## [YoloIP.](https://github.com/Qengineering/YoloIP)
You might also be interested in YoloIP. YoloIP works with everyday surveillance cameras connected to a network.
It can handle up to 8 cameras simultaneously. And, just like YoloCam, events trigger the GPIO and send emails. 

------------

## Hardware.
To get the YoloCam working, you need the following hardware:
- A Raspberry Pi 4, 3B+ or Zero 2W.
- A cheap RPi V1 camera ([$ 6,62](https://www.reichelt.nl/nl/nl/raspberry-pi-camera-5mp-v1-3-rpi-cam-5mp-p314570.html?&trstct=pos_6&nbc=1)), as the deep learning model only works with small image sizes.
- An SD card (min 16 GB) holding all the software.

------------

## Camera.
YoloCam is suitable for RaspiCam models V1 and V2. **YoloCam does not support Camera Module 3**.<br>Because the AI model works with small-sized images, large images are automatically resized to a lower resolution. That's why there is no real need for an expensive, high-resolution camera. A cheap model V1 will do just fine.<br>

### WebCam
With a small adaption in a script, YoloCam also works with most common webcams. Please read the information on this [Wiki page](https://github.com/Qengineering/YoloCam/wiki/WebCam).<br><br>

The YoloCam **email** version has a Nginx web server on board. It feeds an HLS live stream. You can watch it in any browser.<br>
![output image]( https://qengineering.eu/github/YoloBrowser.png )<br>
#### More FPS?
Reduce the resolution of the HLS live stream. Default set at 1296x972 @ 15 FPS. See the [Wiki page](https://github.com/Qengineering/YoloCam/wiki/Nginx-installation#more-fps). 
#### No 10 Sec time lag?
The 10-second time lag is inherent to HLS streaming. There is no workaround.<br>
The only alternative is the GPIO version. This version monitors real-time, with no latency. 

------------

## Software.
There are two versions of the YoloCam software. You have to choose which one you want to use.<br><br>
The _**GPIO**_ version. This version activates the GPIO output pins when a recognized object triggers an event.<br>
There is a live feed to your browser.<br>
The GPIO outputs act in real time. There is no 10-second latency.<br>
Finally, the GPIO version can trigger URLs.<br><br>
The _**email**_ version. This version sends emails and records movies when a recognized object triggers an event.<br>
There is a live feed to your browser. It has a latency of 10 seconds due to the HLS streaming because it takes some time to collect all the information from the stream, get the individual packets and 'glue' them into one video stream. Thanks to this latency, you will receive your emails 5 seconds before the actual movement is visible in your browser so you can log in.<br>The email version lacks the digital zoom function.
#### Tip.<br>
Start with the email version if this is your first time using YoloCam. You get a lot of inside information on everything, with a detailed email to help you tune your events. And for the price, you can't beat it.
![output image]( https://qengineering.eu/images/EmailExampleYoloCam2.png )

------------

## Downloading.
Select the desired version from the matrix below.

| Model  | email | GPIO |
| ------------- | :-----:  | :-----:  |
| Raspberry Pi 4 | [image](https://ln5.sync.com/dl/45158bca0/kscktyzv-ujtn5qs9-2fggujuv-wdetsnir) | [image](https://ln5.sync.com/dl/3edbcedb0/fn7ej3b3-udd5b796-m67wr3j7-zkvyy79z) |
| Raspberry Pi 3B+ | [image](https://ln5.sync.com/dl/72c7fa370/5ctv3tzd-ndzjtjaf-wvrqetfp-ifbkm8wi) | [image](https://ln5.sync.com/dl/bb0bffb50/96yvfptp-mfwnb7js-ri49dxag-jz8vxua6) |
| Raspberry Pi Zero 2W | [image](https://ln5.sync.com/dl/517748e20/2jgfera2-cfmn9uz8-nn6tri35-d37qmqvr)  | [image](https://ln5.sync.com/dl/3e995a560/5c9jwu9x-bc72zp4e-rsdcs6gz-iuy6ur2r) |

username: **pi**<br>
password: **3.14**

------------

## Flashing.
Once the file has been downloaded, flash it to an SD card. Use a good quality SD with a minimum size of 16 GByte for this.<br>
On the [Raspberry Pi website](https://www.raspberrypi.com/documentation/computers/getting-started.html), you can follow the instructions on how to flash an image.<br><br>
Obviously, don't select a standard OS, but the file you just downloaded. For instance' `YoloCam_Rpi4_email.xz`.<br><br>
![output image]( https://qengineering.eu/images/FlashShopRpi.webp )<br><br>
Instead of the [Raspberry Pi Imager](https://downloads.raspberrypi.org/imager/imager_latest.exe), some people prefer [balenaEtcher](https://www.balena.io/etcher/). It doesn't matter, they all do a perfect job.

------------

## First boot.
Insert your fresh SD card into the slot and power your Raspberry Pi.<br>
Because you don't have a license yet, the YoloCam comes with a unique ID to buy the key.<br><br>
![output image]( https://qengineering.eu/images/YoloCamNoKey.png )<br><br>
Follow the instructions and visit the [check out](https://qengineering.eu/checkout.php) site.<br><br>
![output image]( https://qengineering.eu/images/YoloCheckOut.webp )<br><br>
After a successful payment, you receive an email with the 8-digit key.<br>
The instructions on how to unlock the app are shown on the [congratulations page](https://qengineering.eu/congratulations.html).<br>
It is all very simple and self-explanatory.


------------

## Preparations.
Now that you have your license key, a few settings are required for YoloCam to work properly.<br/>
First of all, you need an internet connection. [This page](https://github.com/Qengineering/RPi-image#wifi) explains how to set up the WiFi connection on your Raspberry Pi.<br><br>
Only if you have the **email** version you have to follow the next steps. The GPIO version needs no other settings at this point.
+ You need a Google account to redirect emails and save recorded clips. Since your login details are stored in the Raspberry Pi, we recommend a separate Google account for this application. Just for safety reasons.
+ Register your app with Google to get your email password. Follow the instructions on the Wiki page [Email notification](https://github.com/Qengineering/YoloCam/wiki/Email-notification) on how to set email traffic from your Raspberry Pi.
+ To get the authorization key from Google for gdrive, follow the guide on the Wiki page [Gdrive](https://github.com/Qengineering/YoloCam/wiki/Gdrive-installation#authorization-key). You don't have to install gdrive. It's already on board. You only need the key.
+ Alter the settings to your personal Google account. See for extra information on the Wiki page [Settings](https://github.com/Qengineering/YoloCam/wiki/Settings#settings).
  + `cam_name` Give a name to your YoloCam. Especially useful if you have more than one YoloCam working.
  + `email` The email address that receives the notifications. Note, `none` will block the mail traffic, but not the recording
  + `gmail` The gmail address associated with the Google account above.


------------

## Triggers.
The real beauty of YoloCam lies in its ability to generate triggers when objects are detected.<br><br>
Each recognized object is tested to see if it should trigger an event.<br>
The event can set or reset an output pin in the case of the GPIO version.<br>
Either, send you an email or start a recording if you have the email version.<br><br>
Now it's easy to make a video of your dog chewing your slipper when you're not home.<br>
Or a burglar in your backyard, without your cat always setting off the alarm.<br><br>
The Wiki page [Triggers](https://github.com/Qengineering/YoloCam/wiki/Triggers) gives you all the instructions you need to set the most sophisticated trigger events.<br><br>
![output image]( https://qengineering.eu/images/YoloCamAdGitAdRpi4_4.webp)
> YoloCam on a Raspberry Pi 4

------------

## Overlay.
A less-known fact about SD cards is that they only support a limited number of write cycles. Intense writing wears them out, for example, recording video clips. That's why we enabled recordings on an external USB stick. Or on your Google Drive. Everything to limit writing to the SD card.<br><br>
The best way to protect your SD card from wear and tear is to use the Raspberry Pi overlay feature.<br>
With the overlay active, no writing to the SD takes place, only to RAM.<br>
Another advantage of the overlay is the protection of the SD card against sudden power cuts.<br>
If a power cut happens during a write cycle, it can corrupt the SD card. Worst case scenario, your Raspberry Pi stops functioning.<br><br>
All the more reasons to install an overlay. Please follow the instructions on the [Wiki page](https://github.com/Qengineering/YoloCam/wiki/Overlay).<br>
You might also read the [Wiki page](https://github.com/Qengineering/YoloCam/wiki/Recording) on recordings.<br>

------------

## Specs.

**Rpi 4 and 3B+** OS: Linux raspberrypi 5.15.84-v8+ #1613 Debian GNU/Linux 11 (bullseye) aarch64 GNU/Linux<br>
**Rpi Zero 2W** &ensp; OS: Linux raspberrypi 5.15.56-v7+ #1575 Debian GNU/Linux 11 (bullseye) armv7l GNU/Linux<br><br>

**AP (Average Precision): 25.8 %**<br><br>
Keep in mind that no deep learning model is perfect. Given the limited computing power of the Raspberry PI, we had to make a compromise.<br>
Our network works amazingly well in everyday use. Even small objects in the background are recognized correctly. Likewise, half-cut objects are on the edge of the image. Yet it sometimes makes mistakes. For example, misinterpreting a truck for a car or bus. An understandable error.<br><br>

| Model  | email | GPIO |  Load (Amp) |
| ------ | :--:  |  :--: | :--: |
| Raspberry Pi 4 | 3.7 FPS |  6.0 FPS  | 1.1 |
| Raspberry Pi 3B+ | 2.5 FPS | 3.15 FPS | 1.2 |
| Raspberry Pi Zero 2W | 2.25 FPS | 0.91 FPS  | 0.6 |

**Gdrive video clips: 640x480 @ 15 FPS.**

------------

## Tip.

We used the cheap RPi camera V1 for € 6,66. However, the tiny plug from the embedded sensor to the PCB can be loose. The software still reports the camera but didn't receive any video. It took quite a while before we discovered the cause: the connector. Once glued, it now functions perfectly.<br/><br/>
![output image]( https://qengineering.eu/images/CheapRPiCam.webp)


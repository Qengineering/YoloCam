# YoloCam
![output image]( https://qengineering.eu/images/YoloCamAdGitAd.webp )
## AI camera with live feed, email notification, Gdrive storage and event-triggered GPIO.<br>
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
Given the many hours of work, we ask you for a small one-time fee for the license (€ 12,50).<br>
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
The GPIO outputs acts in real time. There is no 10-second latency.<br>
Finally, the GPIO version has a digital zoom of up to 5X.<br><br>
The _**email**_ version. This version sends emails and records movies when a recognized object triggers an event.<br>
There is a live feed to your browser. It has a latency of 10 seconds due to the HLS streaming, because it takes some time to collect all the information from the stream, get the individual packets and 'glue' them into one video stream. By the way, thanks to this latency, you will receive your emails 5 seconds before the actual movement is visible in your browser so you can log in.<br>The email version lacks the digital zoom function.
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

username: **pi**<br>
password: **3.14**

------------

## Flashing.
Once the file has been downloaded, you need to flash it to an SD card. Use a good quality SD with a minimum size of 16 GByte for this.<br>
On the [Raspberry Pi website](https://www.raspberrypi.com/documentation/computers/getting-started.html), you can follow the instructions on how to flash an image.<br><br>
Obvious, don't select a standard OS, but the file you just downloaded. For instance' `YoloCam_Rpi4_email.xz`.<br><br>
![output image]( https://qengineering.eu/images/FlashShopRpi.webp )<br><br>
Instead of the [Raspberry Pi Imager](https://downloads.raspberrypi.org/imager/imager_latest.exe), some people prefer [balenaEtcher](https://www.balena.io/etcher/). It doesn't matter, they all do a perfect job.

------------

## First boot.
Insert your fresh SD card into the slot and powerup your Raspberry Pi.<br>
Don't be surprised if the initial boot takes a long time. More than three minutes is normal.<br>
We have let [PiShrink](https://github.com/Drewsif/PiShrink) compress the image and make the download time as short as possible.<br>
Another advantage of PiShrink is that you can use SD cards with larger sizes than the original 16 GB.<br>
Because you don't have a license yet, the YoloCam comes with a unique ID to buy the key.<br><br>
![output image]( https://qengineering.eu/images/YoloCamNoKey.png )<br><br>
Follow the instructions and visit the [check out](https://qengineering.eu/checkout.php) site.<br><br>
![output image]( https://qengineering.eu/images/YoloCheckOut.webp )<br><br>
After a successful payment, you receive an email with the 8-digit key.<br>
The instructions on how to unlock the app are shown on the [congratulations page](https://qengineering.eu/congratulations.html).<br>
It is all very simple and self explanatory.


------------

## Preparations.
Now that you have your license key, a few settings are required for YoloCam to work properly.<br/>
First of all, you need an internet connection. [This page](https://github.com/Qengineering/RPi-image#wifi) explains how to set up the WiFi connection on your Raspberry Pi.<br><br>
Only if you have the **email** version, you need the following things to do. The GPIO version need no other settings at this point.
+ You need a Google account to redirect emails and save recorded clips. Since your personal login details are stored in the Raspberry Pi, we recommend a separate Google account for this application. Just for safety reasons.
+ Register your app with Google to get your email password. Follow the instructions on the Wiki page [Email notification](https://github.com/Qengineering/YoloCam/wiki/Email-notification) on how to set email traffic from your Raspberry Pi.
+ To get the authorization key from Google for gdrive, follow the guide on the Wiki page [Gdrive](https://github.com/Qengineering/YoloCam/wiki/Gdrive-installation#authorization-key). You don't have to install gdrive. It's already on board. You only need the key.
+ Alter the settings to your personal Google account. See for extra information the Wiki page [Settings](https://github.com/Qengineering/YoloCam/wiki/Settings#settings).
  + `cam_name` Give a name to your YoloCam. Especially useful if you have more than one YoloCam working.
  + `email` The email address that receives the notifications. Note, `none` will block the mail traffic, but not the recording
  + `gmail` The gmail address associated with the Google account above.


------------

## Triggers.
The real beauty of YoloCam lies in its ability to generate triggers when objects are detected.<br><br>
Each recognized object is tested to see if it should trigger an event.<br>
The event can set or reset an output pin in the case of the GPIO version.<br>
Either send you an email, or start a recording if you have the email version.<br><br>
Now it's easy to make a video of your dog chewing your slipper when you're not at home.<br>
Or a burglar in your backyard, without your cat always setting off the alarm.<br><br>
The Wiki page [Triggers](https://github.com/Qengineering/YoloCam/wiki/Triggers) gives you all the instructions you need to set the most sophisticated trigger events.<br><br>
![output image]( https://qengineering.eu/images/YoloCamAdGitAdRpi4_4.webp)
> YoloCam on a Raspberry Pi 4

------------

## Overlay.
A less-known fact about SD cards is that they only support a limited number of write cycles. Intense writing wears them out, for example, recording video clips. That's why we enabled recordings on an external USB stick. Or on your Google drive. Everything to limit writing to the SD card.<br><br>
The best way to protect your SD card from wear and tear is to use the Raspberry Pi overlay feature.<br>
With the overlay active, no writing to the SD takes place, only to RAM.<br>
Another advantage of the overlay is the protection of the SD card against sudden power cuts.<br>
If a power cut happens during a write cycle, it can corrupt the SD card. Worst case scenario, your Raspberry Pi stops functioning.<br><br>
All the more reasons to install an overlay. Please follow the instructions on the [Wiki page](https://github.com/Qengineering/YoloCam/wiki/Overlay).<br>
You might also read the [Wiki page](https://github.com/Qengineering/YoloCam/wiki/Recording) on recordings.<br>

------------

## Specs.

**Rpi 4 and 3B+** OS: Linux raspberrypi 5.15.61-v8+ #1579 Debian GNU/Linux 11 (bullseye) aarch64 GNU/Linux<br>
**Rpi Zero 2W** &ensp; OS: Linux raspberrypi 5.15.56-v7+ #1575 Debian GNU/Linux 11 (bullseye) armv7l GNU/Linux<br><br>

**AP (Average Precision) : 25.8 %**<br><br>
Keep in mind that no deep learning model is perfect. Given the limited computing power of the Raspberry PI, we had to make a compromise.<br>
Our network works amazingly well in everyday use. Even small objects in the background are recognized correctly. Likewise, half-cut objects that are on the edge of the image. Yet it sometimes makes mistakes. For example, misinterpreting a truck for a car or bus. An understandable error.<br><br>

| Model  | email | GPIO | Zoom 2x | Zoom 4x | Load (Amp) |
| ------ | :--:  | :--: | :--: | :--: | :--: |
| Raspberry Pi 4 | 3.7 FPS |  6.3 FPS | 5.5 FPS | 3.7 FPS | 1.1 |
| Raspberry Pi 3B+ | 2.5 FPS | 2.52 FPS | 2.1 FPS | 1.05 FPS | 1.2 |
| Raspberry Pi Zero 2W | 2.17 FPS | 0.78 FPS | 0.72 FPS | 0.4 FPS | 0.6 |

The GPIO digital zoom works by cropping the frame and resizing it to the native resolution of 640x480.<br>
High zooms require high-resolution video streams, which in turn require more computing power to process, leaving less for the deep learning model. Hence the lower frames per second (FPS).<br><br>
**Gdrive video clips: 640x480 @ 15 FPS.**

------------

## Tip.

We used the cheap RPi camera V1 for € 6,66. It works fine. However, the tiny plug from the embedded sensor to the PCB often can be loose. Somehow the software still supported the camera but didn't receive any video anymore. It took quite a while before we discovered the cause; the connector. Once glued, it now functions perfectly.<br/><br/>
![output image]( https://qengineering.eu/images/CheapRPiCam.webp)


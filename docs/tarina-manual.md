
TARINA BUILD INSTRUCTIONS
=========================

Step by step build instructions for a 3D printable Raspberry Pi video camera. Now, this is still a work in progress and documentation is on its way, if you're in a hurry feel free to drop a message in [#tarina:bennysmatrixchat.ddns.net](https://riot.im/app/#/room/!KHPruVufWZoLpQAUMZ:bennysmatrixchat.ddns.net)

![Tarina and Leon](tarina-and-leon.jpg)

Contents
--------

1. [Get the parts](#get-the-parts)
2. [3d printing](#3d-printing)
3. [Post processing](#post-processing)
4. [Wiring](#wiring)
5. [Putting it together](#putting-it-together)
6. [Installing software](#installing-software)
7. [Tested lenses](#tested-lenses)


Get the parts
=============

![Tarina parts layed out](tarina-build.jpg)

Here is a list of parts that will work, there are other parts that probably will work but this is what I recommend.


Raspberry pi 3 B
----------------
Price ~30 eur

The heart of Tarina. Why Raspberry pi you ask? There are several reasons:

* Huge support.
* The great Debian based os Raspbian (beeing a debian nerd myself).
* Low price.
* Picamera.

The 3B+ is too powerhungry for the Powerbooster 1000C thats why I went with 3B

**Links**
[Raspberry pi site](https://raspberrypi.org)
**Buy**
[Aliexpress](https://www.aliexpress.com/store/product/Raspberry-Pi-3-Model-B-Raspberry-Pi-Raspberry-Pi3-B-Pi-3-Pi-3B-With-WiFi/3242037_32900816535.html?spm=2114.search0104.3.113.7a702274lCPIr4&ws_ab_test=searchweb0_0,searchweb201602_5_10065_10068_5016020_5015416_10059_10696_100031_5015320_10084_10083_10103_451_10618_452_5016116_10304_10307_10820_10821_10302,searchweb201603_55,ppcSwitch_2&algo_expid=0a48bb10-5985-49ff-be76-433eb1f8685b-15&algo_pvid=0a48bb10-5985-49ff-be76-433eb1f8685b&priceBeautifyAB=0)


Arducam 5 MP OV5647 camera module with CS lens
----------------------------------------------
Price ~30 eur

This module and lens gives good hd video quality with the ability to manually focus and replace lenses. See tested lenses down below.

**Links**
[Arducam](http://arducam.com/)
**Buy**
[ebay](https://www.ebay.com/itm/OV5647-Camera-Board-w-CS-mount-Lens-for-Raspberry-Pi-3-B-B-2-Model-B-/281212355128?txnId=1913825600018)


Ugeek 3.5 inch 800x480 TFT Screen
---------------------------------
Price ~35 eur

Best 3.5 inch screen that I could find. Features worth mentioning:

* 800x480 pixels
* Very responsible 11 ms.
* High contrast.
* Sunlight readable.
* I2C Master.

This is not a touchscreen but I dont think touchscreens are good for cameras anyway. 

**Links**
[Raspberrypiwiki](http://www.raspberrypiwiki.com/index.php/3.5_inch_TFT_800x480@60fps)
**Buy**
[Aliexpress](https://www.aliexpress.com/store/product/U-Geek-Raspberry-Pi-3-5-inch-800-480-TFT-Screen-HD-HighSpeed-LCD-Module-3/1954241_32672157641.html)


USB via vt1620a sound card
--------------------------
Price ~1 eur

Really cheap usb soundcard. It has been working suprisingly well. Have not tested other cards yet.

**Buy**
[Aliexpress](https://www.aliexpress.com/item/Professional-External-USB-Sound-Card-Adapter-Virtual-7-1-Channel-3D-Audio-with-3-5mm-Headset/32588038556.html?spm=2114.01010208.8.8.E8ZKLB)


3.7v 7800mAh li-ion Battery
---------------------------
Price ~17 eur

I have tried several batteries, the adafruit 6800mAh is also fine.

**Buy**
[Aliexpress](https://www.aliexpress.com/item/free-shipping-3-7v-7800mah-18650-li-ion-rechargeable-battery-pack-18650-3P-lithium-ion-battery/32823635264.html?spm=a2g0s.9042311.0.0.49ba4c4dyoKkZS)


Adafruit Powerboost 1000C
-------------------------
Price ~23 eur

This is the only power board that I could find with the feature to run the camera and charge it at the same time.

**Links**
[Adafruit](https://www.adafruit.com/product/2465)
**Buy**
[Ebay](https://www.ebay.com/itm/Adafruit-PowerBoost-1000-Charger-Rechargeable-5V-Lipo-USB-Boost-1A-1000C-A/282083284436?epid=2256108887&hash=item41ad7955d4%3Ag%3ALesAAOSwkQZbYXrn&_sacat=0&_nkw=powerboost+1000c&_from=R40&rt=nc&_trksid=m570.l1313)


8x8x5MM DIP-4 Silicone Switch Mute Silent button
------------------------------------------------
Price ~2 eur/20 pcs

You can only buy a pack of 20 pcs but these buttons are good and silent! Not necessary if you want to control with keyboard like Rii mini 8+

**Buy**
[Ebay](http://www.ebay.com/itm/151723036469?_trksid=p2057872.m2749.l2649&ssPageName=STRK%3AMEBIDX%3AIT)


MCP23017-E/SP DIP-28 16 bit I / O expander I2C
-----------------------------------------------
Price ~1 eur

This will be connected to the screen I2C port. This is not necessary if you intend to control the camera with a keyboard like the Rii mini i8+

**Buy**
[Aliexpress](https://www.aliexpress.com/item/10PCS-MCP23017-E-SP-DIP-28-MCP23017-16-Bit-I-O-Expander-with-I2C-Interface-IC/32665631086.html?spm=a2g0s.9042311.0.0.27424c4dn4m008)


2x8cm double side copper prototype pcb
--------------------------------------
Price ~0.20 eur/pcs

PCB board to solder all connections on the MCP23017-E/SP

**Buy**
[Aliexpress](https://www.aliexpress.com/item/5pcs-2x8cm-double-Side-Copper-prototype-pcb-2-8-panel-Universal-Board-for-Arduino-Free-Shipping/32820588012.html?spm=a2g0s.9042311.0.0.27424c4dPM5vVF)


Piezo electronic buzzer
-----------------------
Price ~1 eur

Very useful for timing shots!

**Buy**
[Aliexpress](https://www.aliexpress.com/store/product/New-Arrival-Durable-3-24V-Piezo-Electronic-Buzzer-Alarm-95DB-Continuous-Sound-Beeper-For-Arduino-Car/1959068_32666789405.html?spm=2114.search0204.3.1.4cef4057RBI3xn&ws_ab_test=searchweb0_0,searchweb201602_3_10065_10068_10059_5015413_5015313_10696_100031_10084_10083_5016113_10103_451_10618_452_10304_10307_10820_10821_10302_5016013,searchweb201603_45,ppcSwitch_4_ppcChannel&algo_expid=c84318cd-b50e-4370-9cad-6ae9bc7963ae-0&algo_pvid=c84318cd-b50e-4370-9cad-6ae9bc7963ae&priceBeautifyAB=0)


Latching push button switch mini
---------------------------------
Price ~1 eur/10 pcs

This serves as the microphone and screen on/off button

**Buy**
[Aliexpress](https://www.aliexpress.com/item/10Pcs-Set-1A-30V-DC-250V-Black-Latching-On-Off-Mini-Torch-Push-Button-Switch-G08/32756874522.html?spm=a2g0s.9042311.0.0.27424c4ddFzv3i)


Latching push button switch 10mm
--------------------------------
Price ~5 eur/24 pcs

I use this as the powerbutton. I have tried different versions of safe shutdown buttons for the Raspberry pi but they have not worked as I wanted (they draw power even when Pi is powered off, this is not good). I have solved the problem with a menu button to safely shut down the camera. 

**Buy**
[Aliexpress](https://www.aliexpress.com/item/24pcs-latching-push-button-switch-10mm-fixed-pushbutton-switch-latching-maintained-push-buttons/32770346793.html?spm=a2g0s.9042311.0.0.27424c4ddFzv3i)


Nut 1/4 -20 UNC 304 A2 
-----------------------
Price ~2 eur/10 pcs

This is the standard camera stand nuts. If you never use a stand then you dont need this.

**Buy**
[Ebay](https://www.ebay.com/itm/1-4-20-UNC-304-A2-Stainless-Steel-Hex-Full-Nuts-Qty-10PCS-/222134363896?hash=item33b83d66f8)<br>


MAX9812 Microphone amplifier
----------------------------
Price ~2 eur

This makes suprisingly good sounding sound!

**Buy**
[Aliexpress](https://www.aliexpress.com/item/MIC-microphone-amplifier-module-sound-module-voice-module/32268198506.html?spm=a2g0s.9042311.0.0.3ac34c4dNug0b5)


3.5mm Female stereo headset interior PCB mount
----------------------------------------------
Price ~1 eur/10 pcs

Microphone input.

**Buy**
[Ebay](https://www.ebay.com/itm/10pcs-3-5mm-Female-5-Pins-Stereo-Headset-Interior-PCB-Mount-Audio-Jack-Socket-/252376936189?hash=item3ac2d66efd)


LR44 Batteries
--------------
Price ~2 eur/10 pcs

Microphone batteries

**Buy**
[Aliexpress](https://www.aliexpress.com/store/product/10PCS-Lot-100-Genuine-wholesale-GP-A76-GPA76-LR44-AG13-LR44-SR44-battery-LR44-357-AG13/1120058_32739450265.html?spm=2114.search0104.3.44.5b5d32dbJK5uJ1&ws_ab_test=searchweb0_0,searchweb201602_5_10065_10068_5015418_5016020_10059_10696_100031_5015320_10084_10083_10103_451_10618_452_10304_10307_10820_10821_5016118_10302,searchweb201603_55,ppcSwitch_2&algo_expid=8af0bcbe-dcb8-4f9a-bd47-084a4d77561a-6&algo_pvid=8af0bcbe-dcb8-4f9a-bd47-084a4d77561a&priceBeautifyAB=0)


Screws M3x12mm
-----------
Price ~2 eur/25 pcs

These hold the camera together.

**Buy**
Your local harware store
[Motonet (store in Finland)](https://www.motonet.fi/fi/tuote/389247/Uraruuvi-3x12-A2-RST-25kpl)


Screws 2.2x9.5mm
----------------
Price ~1 eur/20 pcs

These hold the camera/mic together.

**Buy**
Your local hardware store
[Hobbycenter (store in Finland)](https://www.hobbycenter.fi/kavan-puuruuvi-22x95mm-20-kpl-0096a)


LR44 Button cell socket holder
--------------------------------------
Price ~1 eur/pcs

We only need the metal parts from these, if you have som thin metal you could cut these yourself.

**Buy**
[Aliexpress](https://www.aliexpress.com/item/5Pcs-lot-AG13-LR44-Button-Cell-Battery-Socket-Holder-Plastic-Case-TBH-AG13-B/32833837989.html?spm=a2g0s.9042311.0.0.27424c4dE5lqct)


3.5mm Jack to jack aux cable
----------------------------
Price ~1 eur

From microphone to mic-in.

**Buy**
[Aliexpress](https://www.aliexpress.com/store/product/1-Piece-Short-0-2M-20cm-Red-3-5mm-Jack-to-Jack-Aux-Cable-Male-to/505072_32833465555.html?spm=2114.search0104.3.9.383e3c3dVjq9DY&ws_ab_test=searchweb0_0,searchweb201602_5_10065_10068_5016020_10059_10696_100031_5015320_5016120_10084_10083_5015420_10103_451_10618_452_10304_10307_10820_10821_10302,searchweb201603_55,ppcSwitch_2&algo_expid=9ba0b376-e66f-48d2-9ccd-ecc1e8794812-1&algo_pvid=9ba0b376-e66f-48d2-9ccd-ecc1e8794812&priceBeautifyAB=0) 


Rii mini i8+ mini keyboard
--------------------------
Price ~17 eur

Wireless control over camera. You will also need this for wifi settings etc. (Recommended) This is one of the best mini keyboards I've tried. 

**Buy**
[Aliexpress](https://www.aliexpress.com/item/Rii-mini-i8-Russian-English-Spanish-Hebrew-Version-Wireless-Backlit-Keyboard-with-Touchpad-for-PC-Smart/32450468690.html?spm=a2g0s.9042311.0.0.27424c4dKdqpVO)


Parts grand total ~200 eur


3d printing
===========

While waiting for ordered parts lets 3d print the rest of the parts. I recommend printing with a solid 90% infill. Now it is pretty crucial that you have a good calibrated printer so that you don't over/under print. Some parts need to be very precise to work.

You'll find all the 3d parts in the 3d folder.

* [body](https://github.com/rbckman/tarina/blob/master/3d/tarina-body.stl)
* [button-plate-bottom](https://github.com/rbckman/tarina/blob/master/3d/tarina-button-plate-bottom.stl)
* [button-plate-upper](https://github.com/rbckman/tarina/blob/master/3d/tarina-button-plate-upper.stl)
* [hdmi-cap](https://github.com/rbckman/tarina/blob/master/3d/tarina-hdmi-cap.stl)
* [left-side](https://github.com/rbckman/tarina/blob/master/3d/tarina-left-side.stl)
* [mic-body](https://github.com/rbckman/tarina/blob/master/3d/tarina-mic-body.stl)
* [mic-lid](https://github.com/rbckman/tarina/blob/master/3d/tarina-mic-lid.stl)
* [picamera-body](https://github.com/rbckman/tarina/blob/master/3d/tarina-picamera-body.stl)
* [picamera-body-lid](https://github.com/rbckman/tarina/blob/master/3d/tarina-picamera-body-lid.stl)
* [picamera-bridge](https://github.com/rbckman/tarina/blob/master/3d/tarina-picamera-bridge.stl)
* [right-side](https://github.com/rbckman/tarina/blob/master/3d/tarina-right-side.stl)
* [screen-lid](https://github.com/rbckman/tarina/blob/master/3d/tarina-screen-lid.stl)


Post processing
===============

This is still a work in progress...

So far I've come to this conclusion:

* Put 3d printed parts together with screws.
* Sand with sandpaper from rough to finest (from 120 to 400). I like to sand down all corners making them round.
* Dust off.
* Paint.
* Wait til dry.
* Paint again.
* Wait til dry. I like to wait for atleast a day to make it really dry.
* Sand again.
* Paint and wait again.
* Continue like this til you are satisfied with the feel, now I like to have a good grip so I finnish with sanding with 400 grit paper and leave it like that.


Wiring
======

![3d printed and painted, next up sanding and adding one more paint layer](tarina-build-10.jpg)
![Tarina wiring diagram](wiring.png)
![Fitting everything together](tarina-build-04.jpg)
![Building](tarina-build-07.jpg)
![Ready for screen](tarina-build-02.jpg)
![MCP and buttons](tarina-build-08.jpg)
![MCP and buttons](tarina-build-11.jpg)
![Building](tarina-build-07.jpg)
![Sound card ready to be soldered](tarina-build-10.jpg)


Putting it together
===================

Documentation on its way, if you're in a hurry feel free to drop a message in [telegram](https://t.me/tarinadiy)


Installing software
===================

Download latest [Raspbian](https://www.raspberrypi.org/downloads/raspbian/) and follow [install instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md).
[Ssh into](https://www.raspberrypi.org/documentation/remote-access/ssh/) Raspberry Pi and run:
```
sudo raspi-config
```
Expand file system, enable camera and then reboot.
Run this to install git:
```
sudo apt-get install git
```
Git clone tarina and then run install script with sudo:
```
git clone https://github.com/rbckman/tarina.git
cd tarina
sudo ./install.sh
```
You'r ready to rumble:
```
python tarina.py
```
Happy filming!

![Should be looking like this once finnished](tarina-leone.jpg)


Tested lenses
=============

Here is what I'm testing right now.


Yumiki 6-60mm 1/3" CS Lens CCTV Lens IR F1.6 Manual Zoom Manual Iris 
--------------------------------------------------------------------

[Aliexpress](https://www.aliexpress.com/item/6-60mm-1-3-CS-Lens-CCTV-Lens-IR-F1-6-Manual-Zoom-Manual-Iris-for/32793850795.html?spm=a2g0s.9042311.0.0.27424c4dmtk6IZ)


Camera Lens 2.8-12mm Varifocal
------------------------------

This lens is good. Will write a longer review once I have more filming hours.

[Aliexpress](https://www.aliexpress.com/item/Megapixel-Fixed-Iris-HD-CCTV-Camera-Lens-2-8-12mm-Varifocal-HD-Security-Camera-Lens-Manual/32644427822.html?spm=a2g0s.9042311.0.0.27424c4dmtk6IZ)

---

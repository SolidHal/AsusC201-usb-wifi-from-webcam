# AsusC201-usb-wifi-from-webcam


## Why
* Add a usb wifi dongle without losing a usb port, or dealing with a dongle plugged in all the time
* Replace the useless webcam with usb wifi that respects your freedom (ath9k_htc)

## Requirements

* Soldering Iron
* Wifi USB dongle that is supported by the ath9k_htc open source driver
  * I used https://www.thinkpenguin.com/gnu-linux/penguin-wireless-n-usb-adapter-gnu-linux-tpe-n150usb but many different ones have the same chipset
  * For example, the ONKYO UWF-1 (Not ONKYO UWF-1 B  !!!!) seems to be the original manufacturer version of the one I linked above
* Some form of electrical tape (preferably the plastic-y clear yellow stuff)

## Instructions

Opened up the c201 following this guide until you have the frame around the lcd removed: https://www.ifixit.com/Guide/Asus+Chromebook+C201+LCD+Screen+Replacement/60771
Unplug and pry out the glued in webcam module. 

![](images/DSC08231.JPG)

Peeling away the adhesive, you can see the designers printed the pinout on the module!

![](images/DSC08235.JPG)

Well, sort of. 

Using the test pads behind a piece of tape near the connector I found the pinout to be:
 
![](images/DSC08238.JPG)

* Pin 1: Black: 3v3
* Pin 2: Red: D-
* Pin 3: Brown:  D+
* Pin 4: Orange:  GND
* Pin 5: Purple:  GND

and the rest are unconnected.

So now, I chopped off the webcam connector and soldered Black, red, Brown, and Orange to a spare usb port and tested it out with a flash drive I don't care about:

![](images/DSC08242.JPG)


It works!

Now to find a place to stuff the guts of the dongle.

The most space can be found under the "heatsink" / keyboard reinforcement right by where the battery wire run. 
The dongle I bought fit perfectly after taping the wires in a bundle(sorry for the blurry pics, clearer ones below)

![](images/DSC08248.JPG)

![](images/DSC08249.JPG)

Running the webcam cable back along the display cable, soldering it to the wifi dongle, and taping the wire down in places so it won't get pinched by the keycoard/topcase

![](images/DSC08246.JPG)


![](images/DSC08252.JPG)

Once I built the firmware and installed it, it worked perfectly. 

Oh, and I left the now even more useless webcam with the chopped off connector plugged into it back where it belongs for safekeeping.


![](images/DSC08245.JPG)


Firmware build instructions: https://wiki.debian.org/ath9k_htc/open_firmware

Hackaday project with similar webcam: https://hackaday.io/project/3400-toshiba-8071a2gb-webcam-module

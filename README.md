# AsusC201-usb-wifi-from-webcam
Replace your useless webcam with usb wifi that respects your freedom (ath9k_htc)

## Requirements

* Soldering Iron
* Wifi USB dongle that is supported by the ath9k_htc open source driver
  * I used https://www.thinkpenguin.com/gnu-linux/penguin-wireless-n-usb-adapter-gnu-linux-tpe-n150usb but many different ones have the same chipset
  * For example, the ONKYO UWF-1 (Not ONKYO UWF-1 B  !!!!) seems to be the original manufacturer version of the one I linked above
* Some form of electrical tape (preferably the plastic-y clear yellow stuff)
* An hour or two

## Instructions

Open up your c201 following this guide until you have the frame around the lcd removed: https://www.ifixit.com/Guide/Asus+Chromebook+C201+LCD+Screen+Replacement/60771
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

So now, I chopped off the webcam connector and soldered Black, rred, Brown, and Orange to a spare usb port. 



Firmware build instructions: https://wiki.debian.org/ath9k_htc/open_firmware

Hackaday project with similar webcam: https://hackaday.io/project/3400-toshiba-8071a2gb-webcam-module

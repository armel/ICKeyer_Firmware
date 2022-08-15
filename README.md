# ICKeyer Firmware
![core2](https://img.shields.io/badge/M5Stack-CORE2-green)
![aws](https://img.shields.io/badge/M5Stack-AWS-orange)

**First of all, many thanks to all my [donors](#donations)🙏🏻** 

The ICKeyer project allows the IC-705, IC-7300 and IC-9700 produced by ICOM to be equipped with an external touch keyer. This allows you to dedicate the IC screen to the Waterfall while having your Keyer on the M5Stack screen.

# Beta test

For the moment, this project is in private beta test only. 

# Features

The ICKeyer support Voice and CW memories. It allows you to call up the 8 memories stored in the transceiver. 

It is possible to change the transmit mode directly from the central button of the keyer (FM, USB, LSB, CW).

![CW](https://github.com/armel/ICKeyer_Firmware/blob/main/img/cw.png)
![USB](https://github.com/armel/ICKeyer_Firmware/blob/main/img/usb.png)

Each memory could be play 1 time or infinite time, with a delay. It is possible to stop the tranmission at any time, always by the central button of the keyer.

![one](https://github.com/armel/ICKeyer_Firmware/blob/main/img/one.png)
![infinit](https://github.com/armel/ICKeyer_Firmware/blob/main/img/infinit.png)

As usual, a settings menu allow you to manage brightness, screensaver, beep level, etc. 

![Menu](https://github.com/armel/ICKeyer_Firmware/blob/main/img/menu.png)

# Settings

First of all, format a micro SD card in FAT32. 

Then, using a plain text editor, you will create a file that should have the `.ini` extension. for example `IC705BT.ini` if you plain to use the ICKeyer with an IC-705 connect by Bluetooth. 

And now, here is what you will put in this `IC705BT.ini` :

```
; Icom Config
[icom]
icom_model = 705
icom_address = 0xA4
icom_connect = BT
icom_device = 30:31:7D:33:B2:58

; Wifi Config
[wifi]
wifi_ssid = YOUR_SSID
wifi_password = YOUR_PASSWORD

; Proxy Config
[proxy]
baud_rate = 115200
proxy_url = http://192.168.1.32
proxy_port = 1234
```

> This is a similar structure to the settings.h file you used to set up, but in plain text, using a .ini format.  

If you're using an IC-7300, here is an another example with this `IC7300USB.ini` :

```
; Icom Config
[icom]
icom_model = 7300
icom_address = 0x94
icom_connect = USB
icom_device = /dev/ttyUSB0

; Wifi Config
[wifi]
wifi_ssid = YOUR_SSID
wifi_password = YOUR_PASSWORD

; Proxy Config
[proxy]
baud_rate = 115200
proxy_url = http://192.168.1.32
proxy_port = 1234
```

> Important ! Important ! Important ! In USB mode, you need to use the [ICUSBProxy](https://github.com/armel/ICUSBProxy) version 0.0.6 or upper. 

Last, you will need to copy these files at the root of the micro SD Card. That's all.

> You are able to put multiple .ini settings files for all your transceivers. I have got 3 of them for my IC-705 in BT mode, my IC-705 in USB mode and my IC-7300 in USB mode. I put them in this repository. 

# Usage

At startup, you'll see the Ini Loader. Select the `.ini` file you would like to load and... enjoy. 

# Disclaimers 

Because of the systematic plundering of my open source projects by a minority of unscrupulous people, taking advantage of my work to make money, I decided to not open the source code of this project, for the moment.

I was insulted, threatened and blacklisted by these same people (resellers, youtubers, etc.). And even if I know that the majority is behind me, that's enough. 

I believe that a small part of the HamRadio community and some resellers are not yet mature enough to understand Open Source.

This being the case, I will make this firmware available for all, but... 

This firmware is copyright (c) 2022 Armel FAUVEAU and covered by the Berne Convention.

THIS FIRMWARE IS NOT ALLOWED TO BE SOLD, IN ANY WAY. 

THIS FIRMWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THIS FIRMWARE OR THE USE OR OTHER DEALINGS IN THIS
FIRMWARE.

# Credits
 
Many thanks to...

| Project             | Author                                                |  Link                                        |
|:------------------- | :---------------------------------------------------- | :------------------------------------------- |
| M5Stack             | [M5Stack](https://twitter.com/M5Stack)                | https://github.com/m5stack/M5Stack           |
| M5Stack-SD-Updater  | [Tobozo](https://twitter.com/TobozoTagada)            | https://github.com/tobozo/M5Stack-SD-Updater |

Icom and the Icom logo are registered trademarks of Icom Incorporated (Japan) in Japan, the United States, the United Kingdom, Germany, France, Spain, Russia, Australia, New Zealand, and/or other countries.


# Donations

Special thanks to Rolf Schroeder DL8BAG, Brian Garber WB8AM, Matt B-Wilkinson M6VWM, Robert Agnew KD0TVP, Meinhard Frank Günther DL0CN, Johan Hansson SM0TSC, Tadeusz Pater VA7CPM, Frederic Ulmer F4ESO, Joshua Murray M0JMO, Mark Hammond N8MH, Angel Mateu Muzzio EA4GIG, Hiroshi Sasaki JL7KGW, Robert John Williams VK3IE, Mark Bumstead M0IAX, Félix Symann F1VEO, Patrick Ruhl DG2YRP, Michael Beck DH5DAX, Philippe Nicolas F4IQP, Timothy Nustad KD9KHZ, Martin Blanz DL9SAD, Edmund Thompson AE4TQ and Gregory Kiyoi KN6RUQ for their donations. That’s so kind of them. Thanks so much 🙏🏻

If you find this project fun and useful then [offer me a beer](https://www.paypal.me/F4HWN) :) 

You could use the code F4HWN in order to get 5% discount on the [M5Stack shop](https://shop.m5stack.com/?ref=LUxetaH4) 🎁

By the way, you can follow me on [Twitter](https://twitter.com/F4HWN) and post pictures of your installation with your M5Stack. It always makes me happy ;) 
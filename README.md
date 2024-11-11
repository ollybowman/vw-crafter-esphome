# vw-crafter-esphome

This is the yaml code and custom component to read some canbus information from a 2014 VW Crafter / Mercedes Sprinter using Home Assistant and ESPHome.

So far it does the following:

* Locks and Unlocks Doors
* Shows doors open or closed status
* Shows headlight on or off status

The yaml code needs to be compiled to an ESP32 dev board.

Change your_username and your_password under SSID to the username and password of your network. Change your_fallback_password to a passwrod to connect to the esp32 if it doesn't connect to your network.

The my_components folder needs to be put in custom_components/esphome on your Home Assistant server. This is basically a copy of the standard canbus component but adds support for 83.3KBPS which isn't enabled by default.

You need to connect the esp32 to the canbus with a 5v canbus transceiver, 3.3v doesn't seem to work as it doesn't provide enough voltage for CANHIGH. I used this one - https://www.aliexpress.com/item/4000484625524.html

The 120ohm resistor needs to be removed from the circuit board for this to function correctly, nothing needs to be put in it's place. Connect the CRX and CTX pins to pins 4 and 5 on the dev board, connect the VCC and GND to the 5v and GND pins on the dev board and connect CANH and CANL to your CANHIGH and CANLOW in the canbus. 

I have LHD crafter and found a CANBUS hub behind the sidepanel in the footwell on the right hand side, whihc was easy to connect into.

If anyone finds more codes or a better way of doing this please add it.

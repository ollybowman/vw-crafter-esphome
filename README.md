# vw-crafter-esphome

This is the yaml code and custom component to read some canbus information from a 2014 VW Crafter / Mercedes Sprinter using Home Assistant and ESPHome.

So far it does the following:

* Locks and Unlocks Doors
* Shows doors open or closed status
* Shows headlight on or off status

The yaml code needs to be compiked to an ESP32 dev board.

The my_components folder needs to be put in custom_components/esphome in the Home Assistant server. This is basically a copy of the standard canbus component but adds support for 83.3KBPS which isn't enabled by default.

You need to connect the esp32 to the canbus with a 5v canbus transceiver, 3.3v doesn't seem to work as it doesn't provide enough voltage for CANHIGH. I used this one - https://www.aliexpress.com/item/4000484625524.html

Yhe 120ohm resistor needs to be reomved for this to function correctly. 

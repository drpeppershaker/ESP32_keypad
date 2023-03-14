# ESP32_keypad V2

inspired by: 
- https://github.com/sfgabe/OITProjects/tree/master/Baby_Buddy_Keypad 
- https://github.com/jeroenterheerdt/Baby-Buddy-Keypad. 

This DIY macropad uses an ESP32 with [ESPHome](https://esphome.io/).<br>
It has 8 keys, and supports single, double, and triple clicks, long clicks, and click and holds.

Version 1 does not have LEDs, Version 2 uses 16 addressable LEDs to give an 8 pixel backlight and an individually addressable light for each keypress.


## Images
![](/assets/V2/RGB_Lighting_Demo.gif)
Please ignore the poor print quality, haven't had time to recalibrate the printer with the baby here!

![](/assets/V2/Inside_V2.JPG)
All switches now connected to common GND.

## Parts
__Referral links:__
- [8 Cherry MX Switches](https://amzn.to/3YT6VgA)
  - I like the Blues, they're _very_ clicky
- [an ESP32 board](https://amzn.to/41l7mCi)
- [Relegendable Keycaps](https://amzn.to/3SmIaqX)
- [Silicone Wire](https://amzn.to/405DW9x)
  - 22awg or 24awg is what I would pick. 22awg is standard size for GPIO pins, but it's less flexible than the 24awg. Your call here. 
  - The silicone wire for the switches is nice because it's super flexible and is easy to strip when when it's really short.
- [Solid Core Wire](https://amzn.to/3lhCEd2)
  - Solid core wire for wiring up the LED pixels. If you look at my images, I actually used the legs from some resistors, and some spare header pins.
  - If I were doing it again, I would use solid core wire to make life easier when wiring up the LEDs.

Note: if you choose to use the above referral links, I may receive a _very_ small commission from Amazon at no extra cost to you.<br>
If you don't wish to use the referral links above, feel free to use the non-referral links below:

__Non-Referral links:__
- [8 Cherry MX Switches](https://www.amazon.com/dp/B07KMXJ4KG)
  - I like the Blues, they're _very_ clicky
- [an ESP32 board](https://www.amazon.com/dp/B08DR31G4G)
- [Relegendable Keycaps](https://www.amazon.com/dp/B01M023NFK)
- [Silicone Wire](https://www.amazon.com/gp/product/B01LH1FR6M)
  - 22awg or 24awg is what I would pick. 22awg is standard size for GPIO pins, but it's a less flexible than the 24awg. Your call here.
  - The silicone wire for the switches is nice because it's super flexible and is easy to strip when when it's really short.
- [Solid Core Wire](https://www.amazon.com/gp/product/B09BFFJRST)
  - Solid core wire for wiring up the LED pixels. If you look at my images, I actually used the legs from some resistors, and some spare header pins.
  - If I were doing it again, I would use solid core wire to make life easier when wiring up the LEDs.

## Requirements
- [Home Assistant installation](https://www.home-assistant.io)
- [ESPHome integration](https://www.home-assistant.io/integrations/esphome/)

## Case
- I 3D printed my case. I've included two versions of the macropad case. The version I used is _really_ tight. If you don't want to put your soldering skills and smash and cram skills to the test, I also included a slightly taller version as well. I will note that I used a high gauge to really help get things put into the case. Plus, you can actually strip the silicone wire with your fingernails, which makes it a lot easier to trim and adjust the length as needed.
- If you choose to print the V2 version there are cutouts for the LED Pixels. Keep the pixels together in strips of 8. That way you can have one strip of 8 pixels running one direction and have the second row flipped for easier wiring.


## Assembly
- all switches are now connected to common GND and to their respective GPIOs (see ESPHome YAML files)
-- Note, your GPIO pins may be different based on the version of the board you use.
![](/assets/V2/wiring_diagram_V2.png)

## Programming
- Add your ESP device to Home Assistant once detected
- Install esp32_keypad.yaml
- Add your own automations (you can use the one here for inspiration). 
  - Note: this version uses events rather than binary sensors for recording clicks.



## Icons
I've included individual icons, a printable template, and a blank template for printing out your own icons for your relegendable keycaps.
[icons here](../main/icons/)

[Icons for keypad courtesy of Freepik on Flaticon](https://www.flaticon.com/authors/freepik)
[blank template courtesy of X-keys](https://xkeys.com/)

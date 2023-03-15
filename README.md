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
| **Parts**            | **Referral Link**       | **Non-Referral Link**                | **Notes**                                                                                                                                                                                                               |
|----------------------|-------------------------|--------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8 Cherry MX Switches | https://amzn.to/3YT6VgA | https://www.amazon.com/dp/B07KMXJ4KG | I like the Blue switches because  they're *very* click-y                                                                                                                                                                |
| an ESP32 board       | https://amzn.to/41l7mCi | https://www.amazon.com/dp/B08DR31G4G | These are to the cheapest ESP32 boards I could find on Amazon.  Use whatever boards you like                                                                                                                            |
| Relegendable Keycaps | https://amzn.to/3SmIaqX | https://www.amazon.com/dp/B01M023NFK | Originally I went with the grey keycaps, but switched to the  translucent keycaps when I put the LEDs in.                                                                                                               |
| Silicone Wire        | https://amzn.to/405DW9x | https://www.amazon.com/dp/B01LH1FR6M | Silicone wire is helpful for wiring the switches to the board.  They're extra flexible, which helps with the smash and cram at the end.                                                                                 |
| Solid Core Wire      | https://amzn.to/3lhCEd2 | https://www.amazon.com/dp/B09BFFJRST | Solid core wire is practically a requirement to wire up the LED Pixels.  In my prototype I used the legs from a few resistors, and some header  pins. It was a *PAIN* to wire that way. Go with some solid core wire... |
| Addressable LEDs     | https://amzn.to/3yH5whK | https://www.amazon.com/dp/B01DC0J0WS | I used these pixels because all the LED strips I have are low density.  I really wanted to cram two LEDs behind each key switch, and this seems  like the simplest way to achieve that.                                 |

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

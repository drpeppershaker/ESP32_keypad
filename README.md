# ESP32_keypad V2

inspired by: 
- https://github.com/sfgabe/OITProjects/tree/master/Baby_Buddy_Keypad 
- https://github.com/jeroenterheerdt/Baby-Buddy-Keypad. 

This DIY macropad uses an ESP32 with [ESPHome](https://esphome.io/).<br>
It has 8 keys, and supports single, double, and triple clicks, long clicks, and click and holds.


## Images
![](/assets/V2/top_V2.JPG)
Please ignore the poor print quality, haven't had time to recalibrate the printer with the baby here!

![](/assets/V2/inside_V2.JPG)
All switches connected to common VIN.

## Parts
__Referral links:__
- [8 Cherry MX Switches](https://amzn.to/3YT6VgA)
  - I like the Blues, they're _very_ clicky
- [an ESP32 board](https://amzn.to/41l7mCi)
- [Relegendable Keycaps](https://amzn.to/3SmIaqX)
- [Wire](https://amzn.to/3SCjDOE)
  - I like the silicone wire because it's very flexible and easy to work with

Note: if you choose to use the above referral links, I may receive a _very_ small commission from Amazon at no extra cost to you.<br>
If you don't wish to use the referral links above, feel free to use the non-referral links below:

__Non-Referral links:__
- [8 Cherry MX Switches](https://www.amazon.com/dp/B07KMXJ4KG)
  - I like the Blues, they're _very_ clicky
- [an ESP32 board](https://www.amazon.com/dp/B08DR31G4G)
- [Relegendable Keycaps](https://www.amazon.com/dp/B01M023NFK)
- [Wire](https://www.amazon.com/gp/product/B01KQ2JNLI)
  - I like the silicone wire because it's very flexible and easy to work with

## Requirements
- [Home Assistant installation](https://www.home-assistant.io)
- [ESPHome integration](https://www.home-assistant.io/integrations/esphome/)

## Case
- I 3D printed my case. I've included two versions of the macropad case. The version I used is _really_ tight. If you don't want to put your soldering skills and smash and cram skills to the test, I also included a slightly taller version as well. I will note that I used a high gauge to really help get things put into the case. Plus, you can actually strip the silicone wire with your fingernails, which makes it a lot easier to trim and adjust the length as needed.


## Assembly
- all switches are connected to VIN and to their respective GPIOs (see ESPHome YAML files)
-- Note, your GPIO pins may be different based on the version of the board you use.
![](/assets/V2/wiring_diagram_V2.png)

## Programming
- Add your ESP device to Home Assistant once detected
- Install esp32_keypad.yaml
- Add your own automations (you can use the one here for inspiration). 
  - Note: this version uses events rather than binary sensors for recording clicks. I'm looking into whether binary sensors might be a better solution...



## Icons
I've included individual icons, a printable template, and a blank template for printing out your own icons for your relegendable keycaps.
[icons here](../main/icons/)

[Icons for keypad courtesy of Freepik on Flaticon](https://www.flaticon.com/authors/freepik)
[blank template courtesy of X-keys](https://xkeys.com/)

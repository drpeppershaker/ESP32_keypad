# ESP32_keypad

inspired by https://github.com/sfgabe/OITProjects/tree/master/Baby_Buddy_Keypad and https://github.com/jeroenterheerdt/Baby-Buddy-Keypad. 

I made a version of the baby buddy keypad, but I realize that it could actually be used for just about anyting inside Home Assistant, so I decided to make this public.

Differences between this version and the original two apart the physical appearance are:
- Uses ESP32 chip
- adjusted GPIO to match the ESP32 chip I have
- Changed the yaml to a more generic keypad event so this keypad can be used for things other than Baby Buddy

## Parts
__Referral links:__
- [8 Cherry MX Blue Switches](https://amzn.to/3YT6VgA)
- [a ESP32 board](https://amzn.to/41l7mCi)
- [Blank Keycaps](https://amzn.to/3SmIaqX)

Note: if you choose to use the above referral links, I may receive a _very_ small commission from Amazon at no extra cost to you.<br>
If you don't wish to use the referral links above, feel free to use the non-referral links below:

__Non-Referral links:__
- [8 Cherry MX Blue Switches](https://www.amazon.com/dp/B07KMXJ4KG)
- [a ESP32 board](https://www.amazon.com/dp/B08DR31G4G)
- [Blank Keycaps](https://www.amazon.com/dp/B01M023NFK)



- Home Assistant installation with ESPHome
- enclosure (I 3D printed my enclosure)


## Assembly
- all switches are connected to VIN and to their respective GPIOs (see ESPHome YAML files)
-- Note, your GPIO pins may be different based on the version of the board you use.

## Programming
- Add your ESP device to Home Assistant once detected
- Add the Baby Buddy HA Integration if you haven't already.
- Add your own automations (you can use the one here for inspiration - for the battery powered one there are no events being fired, but a sensor will be created that returns the wake reason.).
- You'll need to figure out your baby's entity ID number/name from HA for the automations to log correctly, and decide what notes will be helpful, and change the YAML as needed. You can figure this out by making a test service call from the HA developer section and see what the YAML shows you for entity_id.

## Images
![](top.jpg)

![](inside.jpg)

## Icons
[Icons for keypad courtesy of Freepik on Flaticon](https://www.flaticon.com/authors/freepik)

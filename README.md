# ESP32_keypad V2
<p align="center">
  <img src="https://raw.githubusercontent.com/drpeppershaker/ESP32_keypad/V2/assets/V2/Top_V2.JPG" width=41% height=41% />
  <img src="https://github.com/drpeppershaker/ESP32_keypad/blob/V2/assets/V2/RGB_Lighting_Demo.gif" width = 54% height =54% />
</p>
Please ignore the poor print quality, haven't had time to recalibrate the printer with the baby here!

This DIY macropad uses an ESP32 with [ESPHome](https://esphome.io/).<br>
It has 8 keys, and supports single, double, and triple clicks, long clicks, and click and holds.

Version 1 does not have LEDs, Version 2 uses 16 addressable LEDs to give an 8 pixel backlight and an individually addressable light for each keypress.



## Parts
| **Parts**            | **Referral Link**       | **Non-Referral Link**                | **Notes**                                                                                                                                                                                                               |
|----------------------|-------------------------|--------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8 Cherry MX Switches | https://amzn.to/3YT6VgA | https://www.amazon.com/dp/B07KMXJ4KG | I like the Blue switches because  they're *very* click-y                                                                                                                                                                |
| an ESP32 board       | https://amzn.to/41l7mCi | https://www.amazon.com/dp/B08DR31G4G | These are to the cheapest ESP32 boards I could find on Amazon. Use whatever boards you like                                                                                                                            |
| Relegendable Keycaps | https://amzn.to/3SmIaqX | https://www.amazon.com/dp/B01M023NFK | Originally I went with the grey keycaps, but switched to the translucent keycaps when I put the LEDs in.                                                                                                               |
| Silicone Wire        | https://amzn.to/405DW9x | https://www.amazon.com/dp/B01LH1FR6M | Silicone wire is helpful for wiring the switches to the board. They're extra flexible, which helps with the smash and cram at the end.                                                                                 |
| Solid Core Wire      | https://amzn.to/3lhCEd2 | https://www.amazon.com/dp/B09BFFJRST | Solid core wire is practically a requirement to wire up the LED Pixels. In my prototype I used the legs from a few resistors, and some header pins. It was a *PAIN* to wire that way. Go with some solid core wire... |
| Addressable LEDs     | https://amzn.to/3yH5whK | https://www.amazon.com/dp/B01DC0J0WS | I used these pixels because all the LED strips I have are low density and the Pixels are too spread out. I really wanted to cram two LEDs behind each key switch, and this seems like the simplest way to achieve that. After building two keypads with LEDs, I think that someone who isn't me should attempt this with an LED strip with 144 pixel/m strips. You should be able to fit two leds behind each key with that kind of density.                                 |
| Tiny Screws/Bolts | ... | ... | I used some ~~2.5mm~~ 3mm x 20mm hex bolts for the case, and I think some 2.5mm x 3mm screws to hold the board down.                                                                                                                                                               |

## Requirements
- [Home Assistant installation](https://www.home-assistant.io)
- [ESPHome integration](https://www.home-assistant.io/integrations/esphome/)

## Case
- I 3D printed my case. I've included two versions of the macropad case bottom. The images from V1 is using the 'short_bottom'. The short bottom version of the case makes things *really* tight, but everything should fit if you are careful with your wiring. Run the wires along the sides of the board, and keep them trimmed short. That said, If you don't want to put your soldering skills and smash and cram skills to the test, I also included a slightly taller version as well. The V2 version of the keypad w/ the LEDs that I made was testing my patience already, so I just put it in the taller version of the case. Certainly much easier, and not *that* much taller overall.

- The V2 top case has cutouts for the LED pixels and for the common ground wire. This can be printed without supports, your printer must be at least *kinda* dialed in. You can see my pictures--my printer isn't all that calibrated, and I was still able to print this without supports. The real trick is to print it SLOWLY. The slower you print it, the better chance you'll have of not knocking off the the little center posts, plus your bridging will be better. I dialed my printer back to 35mm/s on both walls and infill and all the way down to 25mm/s for bridging. 
- You will probably want to set your slicer to print the external perimeters first. The case is designed for the key switches to be pressure fit. Printing the outer walls first will help keep the print from over expanding and making your switches not fit. You can also dial back your flow settings to help keep things fitting as they should. If you're still struggling, you can also increase the dimensions of the STLs by 1 or 2 percent to help things fit a bit easier. NOTE: I have not tested printing the case larger, so I don't know how well the LEDs will fit when you size it up.
- Finally, I'm not a 3D designer or engineer. I adapted the original design from thingiverse for my needs using Tinkercad. 
- https://www.tinkercad.com/things/466cJwJKiFd-macropadv2topver37
- https://www.tinkercad.com/things/ekNTHmUWMJU-esp32macropadbottoms


## Assembly
- all switches are now connected to common GND and to their respective GPIOs (see ESPHome YAML files)
-- Note, your GPIO pins may be different based on the version of the board you use. I'm using the built-in PULLUP resistors on the ESP32 board for the switches. If you need to switch GPIO pins, make sure you use pins that have PULLUP resistors.
![](/assets/V2/wiring_diagram_V2.png)

<br><br>
<table>
<tbody>
  <tr>
    <td><img src="https://raw.githubusercontent.com/drpeppershaker/ESP32_keypad/V2/assets/V2/LED_Layout.JPG"></th>
    <td><img src="https://raw.githubusercontent.com/drpeppershaker/ESP32_keypad/V2/assets/V2/Inside_V2.JPG"></th>
  </tr>
  <tr>
    <td>Leds Wired and test fit.</td>
    <td>All switches **connected to common GND** rather than VIN.</td>
  </tr>
</tbody>
</table>




NOTE: When wiring up the LED pixels, you *can* have a single solid wire for all the 5V and one for all the GND contacts. However, the data contacts must be separated and move from DIN to DOUT--they can't be connected on the same pixel or they will NOT work. Stick to the wiring diagram for the Data Line.


## Programming
- Add your ESP device to Home Assistant once detected
- Install esp32_keypad.yaml
- Add your own automations (you can use the one here for inspiration). 
  - Note: this uses events rather than binary sensors for recording multi-clicks.



## Icons
I've included individual icons, a printable template, and a blank template for printing out your own icons for your relegendable keycaps.
[icons here](../main/icons/)



## Credits
inspired by: 
- https://github.com/sfgabe/OITProjects/tree/master/Baby_Buddy_Keypad 
- https://github.com/jeroenterheerdt/Baby-Buddy-Keypad. 

- [Icons for keypad courtesy of Freepik on Flaticon](https://www.flaticon.com/authors/freepik)
- [blank template courtesy of X-keys](https://xkeys.com/)

Special Thanks:
- [jesserockz](https://github.com/jesserockz) & [ssieb](https://github.com/ssieb) on the [ESPHome Discord](https://discord.com/invite/KhAMKrd) for all the support getting this thing working.

# Lampetmeter
#### Meet the Lampetmeter: a photocell-based light detector project that works with Arduino AVR boards!

The Lampetmeter is a simple light detector project for Arduino AVR boards like the Nano, Uno, or Mega. It senses light using a standard CdS photocell (also known as an LDR) and displays it in the unit "Lampets" on a 128x64 OLED display. It features several modes: measurement, histogram, and max, and the mode can be selected via the mode button (S2).

## To build the Lampetmeter, you'll need:
- Arduino (Nano, Uno, or Mega should all work fine)
- 128x64 I2C OLED display
- IRFZ44N N-channel MOSFET
- 2N3906 PNP BJT
- 4x pusbuttons
- Photocell
- 100KΩ resistor
- 10KΩ resistor
- 1KΩ resistor
- 2x 510Ω resistor

## Uploading code
Once you've gathered your components, the next thing you'll want to do is upload the Lampetmeter code to your Arduino. Although it may seem out of order, it's necessary to upload the code before building the circuit so the power latch isn't in the way.

To upload the code:
1. Visit https://github.com/TechTronicsEngineering/Lampetmeter/blob/main/code
2. Click "copy raw file"
3. Open your Arduino IDE, then select anything that might automatically appear in the sketch (e.g. setup and loop)
4. Click paste; the code should appear in the IDE
5. Lastly, click the upload buton in the top left corner of the screen. The code will now upload!

## Building the circuit
Now it's time to start building the circuit! Here's my (hopefully readable) schematic.
![IMG_E1696](https://github.com/user-attachments/assets/757d0b21-ac95-4667-ada4-e55e4dea526f)
Once the circuit is built, just connect a 9V battery between the VCC and ground points. The Lampetmeter is complete!

To use the Lampetmeter, simply press S3 and it will power up, displaying "TechTronics" on the screen for one second.
After booting up, the device should automatically enter the measurement mode, displaying the current number of Lampets on the screen and a small graph at the bottom.
Pressing S1 will reset the current measurment. Pressing S2 will cause the Lampetmeter to enter the histogram mode; where it plots light vs time. Every 1.28 seconds, it will wipe the old graph from the display and begin a new one, and pressing S1 will cause it to do so prematurely.
A second press of S2 will enter the MAX mode. In this mode, the Lampetmeter will display the greatest amount of light it hasdetected since power up. This can be reset by pressing S1.

When you're done with the Lampetmeter, you may turn it off by a press of S4. When powered off, the device will not draw any current from the battery powering it.

## MIT License

Copyright (c) 2025 TechTronics

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

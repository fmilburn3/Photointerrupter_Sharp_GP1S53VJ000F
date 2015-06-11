# Photointerrupter_Sharp_GP1S53VJ000F
Sketch and circuit demonstrating a Sharp GP1S53VJ000F photointerrupter

It has been tested on a Texas Instruments EXP-430F5529 LaunchPad with Energia and on an Arduino Uno. It should work with most LaunchPads using Energia.

The sensor consists of an infrared LED emitter and a phototransistor detector opposite each other in a case. When the transmission between them is blocked the digital pin will go high.  The sketch will then send a message to the serial monitor.

When tested it gave a very reliable response, even in bright sunlight with the sensor unshielded.

Ideas for further development:
1) Use two of them and set up an encoder

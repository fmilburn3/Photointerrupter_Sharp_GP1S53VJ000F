/*
Sketch and circuit demonstrating a Sharp GP1S53VJ000F
photointerrupter. It has been tested on a Texas Instruments
EXP-430F5529 LaunchPad with Energia and on an Arduino Uno.
It should work with most LaunchPads using Energia.

The sensor consists of an infrared LED emitter and a
phototransistor detector opposite each other in a case.
When the transmission between them is blocked the digital
pin will go high.  The sketch will then send a message to
the serial monitor.

When tested it gave a very reliable response, even in bright
sunlight with the sensor unshielded.

Created by Frank Milburn,  8 June 2015
Released into the public domain

Photointerrupter layout from top
--------------------------------
IR LED                                  Phototransistor
          ___________________________
Anode     |  o  |             |  o  |   Emitter          
          |  S  |             | S53 |
Cathode   |  o  |             |  o  |   Collector
          ---------------------------
 
Circuit Design
--------------
Emitter

Infrared emitting Gallium arsenide diode (non-coherent): design 
current limiting resistor for 20mA forward current and 1.25V drop
across LED.
R1 = (3.3 - 1.25) / .020 = 102.5, use 120 ohm

Photodetector

Silicon phototransistor: design for maximum of 75mW and collector
current not to exceed 20mA. Expect Ic to be about 1.8mA based on
Fig.5 and Fig.6 of the datasheet with forward current of 20mA from
the LED and a Collector-emitter voltage of 1V.
R2 = (3.3 - 1) / 0.0018 = 1278, use 1.2k ohm

Circuit
-------
     LED side         Phototransistor side
     
     3V3              GND
      |                |
   R1 = 120 Ohms     E |
      |      IR      | /
     LED    --->     |
      |              | \
     GND             C |________ Pin 2 of microcontroller
                       |
                    R2 =1.2k Ohm
                       |
                      3V3

where E = Emitter of phototransistor
      C = Collector of phototransistor
*/
int photoDetectorPin = 2;    // Any digital pin should work

void setup()
{
  pinMode(photoDetectorPin, INPUT);
  Serial.begin(9600);
  Serial.println("Starting photointerrupter test...");
}

void loop()
{  
  Serial.print("Reading: ");
  int detect = digitalRead(photoDetectorPin);
  Serial.print(detect);
  if (detect == true)
  {
    Serial.println("  detect!");
  }
  else
  {
    Serial.println("");
  }
  delay(100);                // Just a delay to slow things down
}

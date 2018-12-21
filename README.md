# ESP Breakout Board
These are the Eagle files required to have one of these boards made by a PCB manufacturer.
The file ESP32 Board.png is a picture of the assembled board with an ESP32 Dev Kit.
The .zip file contains all the files required by the PCB manufacturer.
The .sch file is the Egle schematic of the board.
The .pdf is a pdf version of the schematic.
The .brd file is the Eagle PCB layout file.
me.lbr is my personal Eagle library. You may need to include this if you modify the schematic or layout as it has the part footprints and symbols.

## This is a collection of three boards manufactured as one board
When you receive these boards you will have to cut them apart to get the three individual boards. There are not guide lines as to where to cut. I use a bandsaw with a metal utting blade to cut them apart. A hacksaw or razor saw will work.

### The ESP Breakout Board
The ESP breakout board can accomodate an ESP8266 dev kit or one of the older ESP32 dev kits that have two rows of fifeteen pins. Newer ESP32 boards use 18 or more pins per row. These will not fit this board.

Each row of GPIO pins has a row of ground pins and a row of 3.3V pins.


The ESP Breakout board has a tri-color LED with current limiting resistors. The LED is accessed by a three pin header. You can use female-to-female jumber cables to wire the LED to any GPIO pin on your dev kit. The LED is common anode, so a low level on the GPIO pin will light up the LED.

The board has a single pushbutton switch with a pullup resistor. A one pin header is used to access the switch. The switch will be normally high and will go low when pressed. You can wire it to the GPIO pin of your choice.

A three pin header/socket is provided for an IR detector or any 3.3V sensor of your choice.  single header pin is provided for wireing to the sensor.

There are pads under the dev kit that can be used to solder down a AS1117 3.3V regulator and associated capacitors (10uf, 10V, Tantalum). The regulator is only needed if your 3.3V loads will exceed the 1 amp capability of the 3.3V regulator on the dev kit. The regulator gets its input voltage from the 5V on the USB interface or the Vin pin of the dev kit. If you install the regulator then you should also isolate the 3.3V pin from the dev kit. This can be done by cutting the trace on the bottom of the board.

This board can also be assembled to work with Witty ESP8266 boards. Witty boards have two rows of eight pins that are 1.2 inches apart. You will need to program the Witty ESP8266 using the mating board that came with it. No provision is made tp program Witty boards in circuit.

### IR Blaster board
This is a simple IR Blaster board. It has an onboard FET the switches the IR LED array on/off. The FET is required due to the high power used by the IR LED array. Six IR LEDs are arranged in an ARC. The IR LEDs used are high power (100ma) and have a fairly wide signal cone. The arrangment is ment to provide the widest possible IR coverage. The board uses 5V to power the LEDs. The LEDs are wired as two in series with a current limiting resistor. Three sets of LEDs are on the board. This board can be used with any microcontroller. Keep in mind that if you use the LEDs called out in the schematic then the board will draw about 300ma when the LEDs are turned on. You can substitute lower power IR LEDs, in which case you will need to adjust the value of the current limiting resistors. You can also reduce the number of LEDs in the array to reduce power.

### HM-11 Breakout Board
This is a breakout board for an HM-11 Bluetooth module. The module is soldered directly to the brakout board. All of the pins of the module are broken out. You can use this board to connect an HC-11 module to any 3.3V microcontroller. The board has a  regulator to drop the 5V input to 3.3V for the HC-11. The GPIO of the HC-11 does not have any level translators. Make sure you only connect to 3.3V devices. Biasing resistors have been added to the inputs that require them. A status LED is provided.

### Misc.
All surface mount resistors are 1206 footprint. The tri-color LED is through-hole, common anode. The resistors on the IR Blaster are 20 ohm, 1/2 Watt thrrough-hole. 
# Tronxy-X5S-Marlin-1.1.9-Firmware
Marlin 1.1.9 Firmware for Tronxy X5S, with SD card, LCD and auto bed leveling


Auto bed level sensor
HOMYL 10-30V DC 300mA Heatbed Position Adjustment Auto Leveling Position Sensor For Anet A8
https://www.amazon.com.au/gp/product/B079NW5VBD/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1 
The pins on this sensors needs to be changed to suit the stock control board.
Brown - +12v 
Blue - GND
Black - Signal (s)


UPDATING MARLIN
The control board on the tronxy x5s needs to be updated. 
An Arduino Uno can be used as an ISP programmer
https://www.arduino.cc/en/Tutorial/ArduinoISP

UPDATING START GCODE 
In the your slicer of choice. 

G21 ; milimeters
G90 ; absolute coords
G1 Z10 ; move the extruder up out of the way
G28 ; Home all axes
M565 Zx.x ; set the Z offset value
G29 ; probe bed
M500 ;Saves bed mesh data to eeprom
G28 X0 Y0 ; home X and Y
G1 Z5.00 F4800 ; get ready to move by lifting the extruder
G1 X100 Y110 F4800 ; move to centre of the bed
G1 Z0.3 ; Move extruder to 0.3mm above the centre of the bed


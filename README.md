# Mini differential IR probe for Z axis, for 3D printer

This is complete set of files to reproduce fork of David Crocker's [Mini Differential IR probe](https://miscsolutions.wordpress.com/mini-height-sensor-board/). Desing is slightly changed. Implemented on Geeetech's acrylic [I3 X clone](https://www.prusaprinters.org/prusa-i3/) of [Prusa I3](https://www.prusaprinters.org/prusa-i3/) 3D printer.

## PCB

It was more quick and cheap to create own PCB for this probe. Gerber files were generated using Spurkfun cam profile, copy is placed in separate directory. [Firmvare](https://github.com/dc42/OrmerodSensorBoard/tree/master/Firmware/Mini-differential-IR/V1.0_1.1) and [schematics](https://github.com/dc42/OrmerodSensorBoard/tree/master/SchematicAndPCB/Mini-differential-IR/V1.0_1.1) used can be found at original DC42's GitHub, version 1.1.
 
#### CAUTION: On photo at the ../Eagle_files you see ver 0.1A with wrong marks of +5V and OUT pins. At version 0.1B there on GitHub is set of correct files.

## Holding bracket

The simplest way to attach this probe to acrylic Geeetech's I3 X is to print out modified version of I3B1-31 bracket. Design is done using FreeCAD (v0.15) instead of Solidworks, for GLP purposes. Holes for screws are only 1.8 mm diam, because it is more simple to drill exact diam for screws you will use instead of correcting CAD file. But if you woulf like to change something - check [modified bracket](https://github.com/liutas4x4/IR-probe_byDC42/tree/master/I3B1-31-Bracket_modified) directory.

## Connecting

This probe is connected to Z_MIN wires on GT2560. If you version of board has only 2 pins, as mine, connect GND to Ground pin of Z_MIN switch, OUT to second pin. Vcc +5 Volts you can obtain from pin on connector for motor driver.

## Calibration

Very first step - applying firmware code changes to you Marlin. Modified configuration.h and configuration_adv.h can be found at of Marlin [there](https://github.com/liutas4x4/Marlin-1.1.X-Geeetech-I3-Pro-X-GT2560). All things you should do after uploading modified firmware are described at Daviv Crocker's [page](https://miscsolutions.wordpress.com/mini-height-sensor-board/), mentioned above.

#### As for December 23, 2017, BILINEAR and LINEAR autoleveling is not working correctly on Geeetech I3, see Issue [#7860](https://github.com/MarlinFirmware/Marlin/issues/7860) for details. Applying bugfix 1.1.X is on the way.

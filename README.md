# the-c128-keyboard-project
This project contains designs for the plate, circuit board, and various 3d-printable bits needed to build a mechanical keyboard for the Commodore 128.

This work is very intentionally licensed for commercial use in the hope that someone will produce and sell these parts in kit and/or assembled form.  See [LICENSE.md](LICENSE.md) for more details.

## Project Goals
1. Provide a replacement keyboard for original Commodore 128 machines.  This is important because the plungers in the original Mitsumi keyboards are prone to cracking and crumbling and the external 128D(CR) keyboards are getting harder to find in reasonable condition.

2. Provide a viable option for those building a new Commodore 128 compatible machine (e.g. using the [C128 NEO](https://c128.se/))

## Configurations
While the goal is to provide fully functional, tested configurations, we're not there yet.  Here's the current status:

|Configuration|Design Complete|Tested|Notes|
|---|---|---|---|
|C128 Flat, re-using original keycaps|Yes|Yes|Fully functional
|C128 Flat, using modern keycaps|No|No|Keycaps not modeled and not commercially available|
|C128 DCR keyboard housing, re-using original keycaps|No|No|Fits in enclosure, but DCR keycaps use stabiliers not currently supported by the plate|
|C128 DCR keyboard housing, using modern keycaps|No|No|Stabiliers not currently supported by the plate.  Keycaps not modeled and not commerically available.|

## Plate design
The plate is designed to be laser cut from .060" cold rolled steel sheet (~1.5mm thick).  The [step file](plate/plate.step) is all you should need to send to a laser cutter.  The keyswitch cutouts are just a little roomier than the typical 14mm squares to accommodate powder coating, which I highly recommend.

## PCB design
The PCB is a simple 2-sided board so it should be easy enough to find a suitable manufacturer.  I used [PCBWay](https://www.pcbway.com/).  A few passives and 4 ICs are needed to make the latching keys (capslock, shift lock, and 40/80).  See [BOM.csv](pcb/bom.csv) for specific part numbers.  Note that while these parts are surface mount, I've found them large enough to hand solder even with my moderate ham-handedness.

## Printables
I've had success printing all the printable parts with a Bambu X1C wielding a .4mm nozzle with the following settings:
- .12mm layer height
- .2mm initial layer height
- 3 wall loops
- 4 top shell layers

I typically keep batches of keycap adapters small (10-12 parts per batch) to keep them consistent.  I would imagine that resin printing would be optimal in terms of quality and consistency, but that is untested.

## Keyswitches
If you're planning on reusing your stock Commodore 128 keycaps, I recommend Outemu mid-low switches, which are about 60% of full throw and keep keycap height very close to the original, despite the keycap adapters.  You'll need to print a sufficient supply of the adapters in the [printable parts](printable_parts) directory.  Alternatively, you could use full-height cherry-compatible switches and modern keycaps, though that configuration is untested for clearance and keycap height.

## Cabling
A [printable 1x25 pin cable end](printable_parts/connector_keyboard_side.stl) is included and has worked well for me.  For the Commodore 128 flat, the [motherboard side of the keyboard connector](printable_parts/connector_motherboard_side.stl) is also modeled.  This connector is an odd combination of DB25 spacing with molex kk-style pins and was not something I could source from typical suppliers.  Cabling for the 128D(CR) external keyboard has not been sorted out yet but should be feasible by simply cutting one end off a DB25 straight-through cable.

## To Do
I'd love some help from the community to accomplish the following:
- Model a Cherry-compatible set of keycaps for printing or (ideally) injection molding
- Model a compatible external enclosure: Allowing complete replacemend 128D keyboards to be built
- Design a cabling solution for 128D keyboards
- Set up a group buy for kits and/or assembled keyboards

## Authors
[Jeff Flitton](mailto:jeff@flitton.dev) - Project creator, plate and printable part designer

## Credits
[Original PCB design](https://codeberg.org/jgrip/c128-keyboard) by [Johan Grip](https://codeberg.org/jgrip/), maker of the [C128 Neo](https://c128.se/).  Minor fit adjustments and latch circuit changes were made.

## Disclaimer
This project is provided as-is, without any express or implied warranty.
By using, building, or modifying this hardware, you acknowledge that you do so at your own risk. The authors and contributors are not responsible for any damage, data loss, injury, or other consequences resulting from its use.

This project is a community-driven, open-hardware design intended for educational and hobbyist use. It is not affiliated with, endorsed by, or supported by Commodore International or any successor entities.

All trademarks, including “Commodore”, “C128”, and related names, are the property of their respective owners and are used here for descriptive and compatibility purposes only.

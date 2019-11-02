# Marlin-A10 3D Printer Firmware
<img align="right" src="buildroot/share/pixmaps/logo/marlin-250.png" />

This fork of Marlin 1.1.9 was created to provide ongoing firmware updates for the Geeetech A10 3D printer model. Its goal is to replicate the "out-of-the-box" experience of the stock firmware by using known-good configuration values and focusing on features that the majority of users will find a necessity.

Marlin 1.1.9 is the final release of the AVR-only flat version of Marlin Firmware, so there will be no further 1.1.x releases. However [`bugfix-1.1.x`](https://github.com/MarlinFirmware/Marlin/tree/bugfix-1.1.x) will continue to receive patches for critical bugs. These will be merged here as soon as possible.

Work on Marlin 2.0 support is planned to start on its first production release. Geeetech printers that are similar to the A10 like the A10M are currently not explicitly supported for lack of testing hardware. **This firmware has only been tested on the most recent A10 revision with a GT2560 v3 board.** The GT2560 rev. B is most likely compatible. However, in any case, there are no warranties.

This project is not affiliated with Geeetech in any way.

## BLTouch Branch

This branch of Marlin-A10 is preconfigured to work with a BLTouch or 3D Touch bed leveling sensor mounted on the bracket that comes with the A10 printer. It uses bilinear bed leveling with 9 probe points by default.

The Z-axis endstop should be disconnected and the sensor connected to the header on the circuit board at the back of the hotend. If your sensor follows the common colour scheme, it needs to be plugged in following this order (viewed from the back of the hotend):

| 1     | 2   | 3      | 4     | 5     |
|-------|-----|--------|-------|-------|
| Brown | Red | Orange | Black | White |

The sensor must be mounted in such a way that the bottom of the probe extends below the nozzle when extended, and does not when retracted. The nozzle could run into the bed or the sensor catch on your prints if this is not given attention to.

After flashing this firmware version, first move the Z axis up a bit and run `Control > BLTouch > BLTouch Self-Test` to make sure the sensor is deploying properly. It will continue extending and retracting until you reset it. Then you can run your first auto homing and hope for the best. To calibrate the sensor, run the bed leveling routine (with properly adjusted corners, and possibly a preheated bed to increase accuracy), disable soft endstops under `Prepare > Move axis` and then move the Z axis down until it catches the leveling shim of your choice. Copy the Z offset to `Prepare > Bed Leveling > Probe Z Offs` (keeping in mind the negative sign) and store your settings. Remember to reenable soft endstops.

## Contributing to Marlin-A10

Contributions of any kind are highly welcome. This especially includes testing and tweaking the configuration. If you find that a value other than the default works better for you, please [search for an open issue](https://github.com/jakobend/Marlin-A10/issues) about it or open one if you don't find one.

Download earlier versions of Marlin on the [Releases page](https://github.com/MarlinFirmware/Marlin/releases). (The latest tagged release of Marlin is version 1.1.9.)

- `bugfix-1.1.x` tracks the [upstream branch](https://github.com/MarlinFirmware/Marlin/tree/bugfix-1.1.x) of the same name.
- `a10` contains configurations specific to the A10.
- `a10-bltouch` is preconfigured to work with the BLTouch or 3D Touch bed leveling sensors.
- `a10-custom` contains customizations specific to my personal setup.

## Configuration sources

- [Geeetech A10 Firmware Marlin 1.1.9](https://www.thingiverse.com/thing:3063754) by Thingiverse user [runUNDfun](https://www.thingiverse.com/runUNDfun)
- [Marlin 1.1.8 stock firmware](https://github.com/Geeetech3D/Prusa_I3_3Dprinter/tree/master/A10_marlin1.1.8) by Geeetech

---

### For information on Marlin itself, visit [marlinfw.org](http://marlinfw.org) or the [README of Marlin 1.1.x](https://raw.githubusercontent.com/MarlinFirmware/Marlin/1.1.x/README.md).

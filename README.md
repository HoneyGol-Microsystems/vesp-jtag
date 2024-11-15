# ![vesp-jtag logo](logos/vesp_logo.png)
An Open Source Hardware JTAG/UART/GPIO interface board based on the amazing [Steppenprobe](https://github.com/diegoherranz/steppenprobe) containing Pmod-compatible connector.

## Basic specs:

- Open Source Hardware and designed in [KiCad](https://kicad.org).
- Majority of footprints have easy to solder 0805 packages.
- [FT2232H](https://ftdichip.com/products/ft2232hl)-based.
- Simultaneous operation of JTAG/UART or GPIO/UART (software-configurable).
- Standard Pmod connector for direct connection to a compatible FPGA.
- Signals also available on 2.54 mm pin header to work with any custom pinout.
- USB powered: no power supply needed.
- USB type-C receptacle: more convenient (reversible) and future-proof.
- 2 GPIO and 2 user-controllable LEDs.
- I/O buffers for protection and compatible with a wide voltage range (1.65 V to 5.5 V).
- Descriptive LED indicators.
- (TODO) OpenOCD compatibility.

*Please note that the board itself is wider than the Pmod standard allows, therefore it is not entirely "Pmod compatible". It may happen that if Pmod ports on your FPGA board are too close to each other, another Pmod board will not fit next to the vesp-jtag at the same time.*

## Schematic PDF, Gerbers and other generated files:
See [releases](https://github.com/HoneyGol-Microsystems/vesp-jtag/releases).

## FTDI channels

The FT2232H has 2 independent channels. In this board:

- Channel A: Used as a JTAG or GPIOs
- Channel B: Used as an UART.

After enumeration, both channels will default to the UART mode, so on a Linux system they will show up as `/dev/ttyUSB0` and `/dev/ttyUSB1`. When the channel A gets reconfigured to a MPSSE mode (e.g. when using OpenOCD with it), then `/dev/ttyUSB0` will disappear and the channel B will remain as `/dev/ttyUSB1`.

## 3D renders

![PCB top view](images/PCB_render_top.png) ![PCB bottom view](images/PCB_render_bottom.png) ![PCB isometric view](images/PCB_render_iso.png)

## OpenOCD example commands
TODO
# KLOTZ BUILDGUIDE (WIP)

## PART LIST

### REQUIRED PARTS

| Part name         | Count | Remarks | 
| :---------------- | :---: | :------ |
| KLOTZ PCB         | 02 | You can find the files for it [here](/PCB/) |
| KLOTZ switchplate |
| Nice!Nano         | 02 | Alternatively, you can use another controller with similar pinout and bluetooth capabilities like the Puchi-BLE |
| Choc key switch   | 34 | Kailh Choc low profile keyswitches |
| diodes 1N4148W    | 34 | These are surface mount diodes in SOD123 package. |
| 1u Choc keycaps   | 34 | You can use the black or white keycaps from Kailh, but I recommend MBK keycaps |
| reset button      | 02 | Through-hole, 2 pin tactile buttons |
| power switch      | 02 | MSK12C02 |
| EC12 encoder      | 02 | Technically you could also use EC11 encoder, but flat EC12 like the EC12E2440301 will work best |
| encoder knob      | 02 | Nearly every encoder knob, which works with the EC12 should work. But if you have acces to a printer you can use [this one](/knob/) |
| USB cable         | 01 | For connecting the keyboard with your PC |
| Lipo battery      | 02 | You can use a variety of Lipo batteries, but the cutout in the switchplate is meant to be used with a battery which name ends with 2030, like the 902030.


### OPTIONAL PARTS

| Part name              | Count | Remarks | 
| :--------------------- | :---: | :------ |
| MCU sockets            | 04 | For socketing your MCU. Highly recommended |
| MCU pins               | 48 | In combinatin with the MCU sockets |
| JST Jack               | 02 | JST PH |
| switch socket          | 34 | Switch sockets for Kailh choc switches |
| LEDs                   | 06 | 3mm through hole LEDs |
| resistors              | 06 | R1206 220ohm SMD resistors for the LEDs |
| screws  				 | 10 | 6mm M2 screws |
| bolts                  | 10 | M2 bolts |
| o-rings                | 10 | as optional standoffs |
| [tenting puck](https://splitkb.com/products/tenting-puck)| 02 | SplitKB Tenting Puck |



## INTRODUCTION

Here is an overview of where and on which side each component needs to be soldered (click on the image to see a larger version).

![KLOTZ solder guide](/docs/images/KLOTZ_solderguide.png)

To see what component needs to sit where you can take a look at the [interactive HTML BOM](https://htmlpreview.github.io/?https://github.com/GEIGEIGEIST/KLOR/blob/main/docs/klor_rev1-3_ibom.html).

> **Warning**
> This interactive HTML BOM does show where each component is located, but please still refer to the solder guide above to see if a component needs to go on the front or back of the PCB.

***

## DIODES

The diodes needs to be soldered on the bottomm of the PCB. Pay attention to their orientation:  They have a small line on one side, which should be on the side the arrow on the PCB is facing to.

<p align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="/docs/images/buildguide/diodes_dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="/docs/images/buildguide/diodes_bright.svg">
  <img alt="diode orientation" src="/docs/images/buildguide/diodes_dark.svg">
</picture>
</p>

Apply a small amount of solder on one pad.\
Then use tweezers to place the diode on the pads and reheat the solder to secure the diode.
Now you can solder the second pad.

![Soldered diode](/docs/images/buildguide/diode_in_place.jpg)
***image***

***

## SWITCH SOCKETS

Here you can apply the same technique as used for the diodes: Apply some solder on one of the pads first.\
Then place the switch socket in the silk screen markings and reheat the solder. Apply some pressure with a pair of tweezers to make sure the socket is fully seated.\
Now solder the second pad.

![switch socket soldered](/docs/images/buildguide/switchsocket.jpg)
***image***

***

## POWER SWITCHES

Apply a tiny bit of solder on one of the bigger, outer pads on the bottom of the PCB. The power switch has some tiny knobs on its bottom, which fits into the PCB holes. Hold it in place with tweezers and than reheat the solder on the pad. After this you can solder the other pad and the three pins.

![power switch](/docs/images/buildguide/power_switch.jpg)
***image***

***

## RESET SWITCHES

Put the legs of the reset switch through the holen on the top of the PCB. 

**image**

You can secure it with some tape, since you need to solder it from below.

![reset switch](/docs/images/buildguide/reset_switch.jpg)

**image**

***

## MICROCONTROLLER

> **Warning**
> First flash the microcontroller to make sure it works, before soldering it in.

The microcontroller needs to be mounted on the top, with the components facing downwards (to the PCB).\
Feel free to use the included header pins, but it's highly recommended to use MillMax low profile sockets.\
Place the sockets in the marked spots on the bottom side of the PCB.

![MCU sockets](/docs/images/buildguide/MCU_sockets.jpg)
**image**

You can keep them in place by using masking tape.\
Then you can flip the board to solder in the sockets from the top.\
Flip it again and insert the pins into the sockets.\

> **Note**
> Use tweezers to insert them. Don't apply too much force, you will feel them snap in. After that, you can carefully apply some pressure, using a flat object to make sure they're fully seated. 

Now place your microcontroller on the pins (components facing the PCB) and solder it to them.\
You can use flush cutters to trim the header pins.

![MCU solder](/docs/images/buildguide/MCU_solder.jpg)
**image**


> **Warning**
> When trimming with flush cutters wear eye protection or hold your hand close above the pins. Otherwise sharp metal pins flying around might hurt you.

***

## RESITORS (optional)

***

## LEDS (optional)

***

## ENCODERS

> **Note**
> Currently ZMK only supports encoders on the primary side of split keyboards. 

Mount the rotary encoder on the top side of the PCB. It should click into place maybe requiring a firm press. If it's seated correctly solder the pins on the bottom.

![encoder](/docs/images/buildguide/encoder.jpg)
**image**

***

## CLEANING

This is how your finished PCB probably will look like. You can use an old toothbrush and some isopropanol to clean it from residues. 

![Finished PCB](/docs/images/buildguide/PCB_finished_BLE.jpg)
***image***

***

## FIRMWARE

If you have not already flashed the firmware to the microcontroller you should do it now, to make sure everything works, before inserting everyting into the case.\
[Here](https://github.com/GEIGEIGEIST/zmk-config-klotz) you can find the ZMK firmware for the KLOTZ.\
You need to create an own fork of it. In this fork you can edit the keymap to trigger an Github action, which will create your firmware. 

***

## BATTERY 

***

## SWITCHPLATE

***

## KNOB

***

## FINAL BUILD

This is how the final keyboard will look like. In this picture you see it with Pseudoku CS keycaps on homing keys and thumbs, the other keycaps are MBK blanks.

![KLOR acrylic case](/docs/images/buildguide/acrylic_case.jpg)
***image***
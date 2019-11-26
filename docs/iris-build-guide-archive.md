# Iris Build Guide Archive

## Please use the following guide: [Updated build log for Rev. 2.1b/2.4/2.5](iris-rev2-build-guide.md)

LED fix for right PCB of Rev. 2.1b or 2.4, in case you soldered the MOSFET to the side with the bad trace: [Rev. 2.1b/2.4 LED Fix](iris-led-fix.md)

##

##

##

## Older Build Log for Rev. 2.0 to 2.1a:

**The guide below is just for reference for those with older PCBs, please see the link above for newer PCBs**

Imgur Album: [Iris Build Log](https://imgur.com/a/iQH2W)

## ![](https://s3.amazonaws.com/docs.keeb.io/assets/images/iris/uqIwtGy.jpg) {#parts-list}

## Parts List {#parts-list}

Here's a list of parts needed for the build:

* 2 [Iris PCBs](https://keeb.io/products/iris-keyboard-split-ergonomic-keyboard)
* 54-56 [diodes](https://keeb.io/products/1n4148-diodes) \(through-hole and SMD diodes supported\)
* 2 [Arduino Pro Micros](https://keeb.io/products/pro-micro-5v-16mhz-arduino-compatible-atmega32u4)
* 2 push buttons for resetting
* 54-56 [switches](https://keeb.io/products/gateron-switches) \(MX-compatible and Alps switches are supported\)
* Case
* 2 [TRRS jacks](https://keeb.io/products/trrs-jacks-3-5mm-one-pair)
* 1 [TRRS cable](https://keeb.io/products/trrs-cable)
* Optional parts
  * 2 4.7kΩ resistors if doing I2C
  * 2u PCB mount MX stabilizers if using 2u keys
  * For LEDs:
    * Rev. 2.1a and lower:
      * 2 100Ω resistors \(one used for each half\)
      * 2 100kΩ resistors \(one used for each half\)
    * Rev. 2.1b and newer:
      * 2 4.7kΩ resistors \(one used for each half\)
    * 2 N-channel MOSFETs
    * 56 470Ω resistors \(or whatever value is appropriate for the LEDs you are using\)

## Build Steps {#build-steps}

Here's a summary of the build steps:

1. Solder components
   1. Solder diodes
   2. Solder push button and TRRS jacks
   3. Solder I2C resistors \(optional\)
   4. Solder LED components \(MOSFET and resistors\) \(optional\)
   5. Solder Pro Micro header pins
2. Add 2u stabilizers
3. Solder switches
4. Solder LEDs
5. Flash Pro Micros
6. Solder Pro Micros
7. Solder RGB strip \(optional\)

## Solder Components

The diodes, resistors, MOSFETs, push buttons, TRRS jacks,, and Pro Micro header pins can be soldered in any order.

### Solder diodes

All the diodes are oriented with the line towards the bottom. All the resistors are oriented horizontally, direction doesn't matter. The PCB supports both SMD and through-hole diodes and resistors, SMD ones are shown here. For through hole diodes, the black line will be at the bottom, towards the square pad.

![](https://s3.amazonaws.com/docs.keeb.io/assets/images/iris/PS0GEXA.jpg)

Through-hole resistors shown here, note that the black line on the diodes are all facing down at the square pad.![](https://s3.amazonaws.com/docs.keeb.io/assets/images/iris/j3do2SU.png)

### Solder reset push buttons and TRRS jacks

### ![](https://s3.amazonaws.com/docs.keeb.io/assets/images/iris/YqDm7vj.jpg)Info about resistors in the kit

The color coded lines on the resistors can be hard to read/decipher, so the paper from the tape reel have been marked with different color lines.

* No Line - 4.7kΩ resistors for I2C \(only used on master half\)
* Blue Line - 100kΩ resistors for MOSFET \(1 for each half\)
* Red Line - 100Ω resistors for MOSFET \(1 for each half\)![](https://s3.amazonaws.com/docs.keeb.io/assets/images/iris/zz1rnXv.png)Some of the PCB kits may have these unlabeled resistors instead of the ones in the previous picture. Here's how to distinguish between them by looking at the bands:![](https://s3.amazonaws.com/docs.keeb.io/assets/images/iris/HmEYzag.png)

### Solder I2C resistors \(optional\)

The default firmware for the Iris uses serial communication between the two halves using a single pin of the TRRS cable. Serial communication only allow for communication between two parts, which is fine for almost all builds.

However, in the future, there might be additional parts that you can add, like a numpad, OLED screen, etc. To support this, the communication protocol would need to be switched over I2C, which can support multiple devices. To add support for I2C, all you need to do is add the 2 4.7kΩ resistors to one of the halves \(other half does not need them\). Also, it doesn't hurt to add these resistors if using serial communication.

tl;dr: Adding this is optional, but you might as well do it as it's only 2 more components to solder.

Left half shown here:![](https://s3.amazonaws.com/docs.keeb.io/assets/images/iris/CUjnMP3.png)

Right half, note that the two spot for the 4.7kΩ resistors are left empty:![](https://s3.amazonaws.com/docs.keeb.io/assets/images/iris/MQFqGEo.jpg)

### Solder LED support components \(optional\)

For each half, add 1 MOSFET, 100Ω resistor, and 100kΩ resistor.![](https://s3.amazonaws.com/docs.keeb.io/assets/images/iris/2rwjJRf.jpg)

To solder the MOSET on, first add a little bit of solder to one of the pads on the PCB. Then position the MOSFET over the pads and heat up the pad to solder the first leg into place. It helps to use a pair of tweezers to hold the MOSFET and position it while heating up the pad.![](https://s3.amazonaws.com/docs.keeb.io/assets/images/iris/k3cwV69.png)

Once the first leg of the MOSFET has been positioned properly, solder the other 2 pads.![](https://s3.amazonaws.com/docs.keeb.io/assets/images/iris/FXKesdZ.png)

Next, add all of the resistors for each switch. 470Ω resistors are commonly used, but this value might vary, based on the LEDs you use and the amount of current they draw.

Solder the resistor in the area of the Pro Micro on the other side \(top side\), so it is out of the way of the Pro Micro when you install it. Alternatively, you can just install all of the resistors on the top side.![](https://s3.amazonaws.com/docs.keeb.io/assets/images/iris/tazkMue.png)

Lone resistor soldered on the top side.![](https://s3.amazonaws.com/docs.keeb.io/assets/images/iris/DGoQ3U0.png)

### Solder Pro Micro header pins

### Solder switches

### Solder LEDs

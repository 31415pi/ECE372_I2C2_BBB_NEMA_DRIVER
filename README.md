This project utilizes the Beaglebone Black platform featuring the ARM Cortex-A8 AM335x 1GHz Sitara Processor.  

We will be utilizing the I2C2, GPIO, Clock, Timer5 and Interrupt peripherals embeddedon the device. BBB  GPIO  Pin  19  and  20  will  be  used  to  interface  the  I2C2  peripheral  output  with  HW-052(PCA9685). This is written in C with embedded assembly in places.  

The HW-052 is a I2C addressable, 16-channel, PWM generating breakout for the PCA9685IC. It features external driver power delivery and isolated control voltage. The slave address is adjustable via jumpers for easy I2C stacking of multiple HW-052 boards.

Figure 1:  HW-048 Schematic

The  PWM  outputs  from  the  HW-052  will  be  used  as  step  functions  to  drive  the  AIN2,  AIN1,BIN1, and BIN2 pins of a HW-048 (TB6612FNG). 

The HW-048 is a Polulu-clone ”stepper motor driver” H-Bridge  breakout  for  the  TB6612FNG  IC.  It  features  EMF  protection,  voltage  smoothing,  and  dual PWM-driven step function output.

![TruthTable](https://github.com/31415pi/ECE372_I2C2_BBB_NEMA_DRIVER/blob/main/Images/tb66_direction.png)
Figure 2:  Truth Table for TB6612 IC

Using both sets of the HW-048 output it is possible to have highly precise operation of a bipolarstepper motor.  We will be using a Sainsmart 17-HSR-1006-25 BET nema motor (2014-05-14 manufacturingdate). Part 1 is simply finding success with sending any data on the I2C output. Part 2 will be utilizing the protocol and peripherals to demonstrate controlled rotational movementof the NEMA motor shaft both in clockwise and counterclockwise directions.

---
layout: default
title: Motors
parent: Common hardware
nav_order: 2
---

- TOC
{:toc}

---

# Supported motor types

FFBeast project based on **BLDC (BRUSHLESS) motor**.

{: .warning }
>**There is no DC or Stepper motor support!**
 
Virtually any BLDC motor with three phases will work, ranging from hobby-grade to industrial.
The performance of the final device will be determined by the characteristics of the motor you choose. A motor capable of producing more torque will result in a stronger final device.

Number of different BLDC motors was tested for this project. And all of them worked.  

## Hobby grade RC motors
First attempts to build joystick were using this kind of motor. In general - them work.
But even motors with the lowest kV are pretty weak and do not produce good force. 
<img src="../../assets/images/showcase_RC_1.jpg" width="720">

## Robotic actuators
Tested in attempts to find motors with higher power. Works!
Have good power, but because of planetary reducer those actuators have significant backlash. 
And them are not the cheapest option. So I do not use them in my projects. 
If you need extremely compact, powerful solution and there is a budget - could be an option.

<img src="../../assets/images/showcase_robotic_1.jpg" width="720">

## Industrial servo motors 
AC servo motor is a good option if you are not restricted in budget. As servo motors are not cheap.
But there are examples when people did use it.

<img src="../../assets/images/showcase_servo_1.jpg" width="720">
<img src="../../assets/images/showcase_04.jpg" width="720">

{: .warning }
>**It need to be AC servo. With 3 phases. DC or Stepper motors are not supported!**


## Howerboard/Scooter motor
<img src="../../assets/images/motor65.jpg">

As of now, the hoverboard/scooter motor is considered **the best alternative** in terms of the **price-to-torque ratio**.
It can be as affordable as **10 USD** per item on the second-hand market, offering a peak torque of **up to 15Nm**. 
You can find them as standalone units or as part of refurbished hoverboards. 

Simply search your local second-hand market, and you're likely to come across some excellent propositions.

### Are them all equal?
Unfortunately - NO!

Despite the similar external dimensions of these motors, they can vary internally. The motor's power is determined 
by the width of the stator, the diameter of the stator, and the number of strands in the motor winding

The most powerful items have stator width 30mm and 300mm magnets. It is coupled with 5 strand in motor winding.
<img src="../../assets/images/big_stator.jpg">

Less powerful items could have 25mm, 20mm or even 15mm stator width and less strands in winding wire.

<img src="../../assets/images/small_stator.jpg">

{: .important }
> It is important to understand, that any such motor will work, despite of internals.
> The main difference will be in peak motor torque (and so peak force that device can produce)

### Real world torque results
As already multiple motors come through the project there is some statistics about torque of such motors. 

{: .important }
>All values there measured at 15A current!

| Stator width(mm) | Magnet length(mm) | Strands in wire | Torque(Nm) |
|------------------|-------------------|-----------------|------------|
 | 30               | 30                | 5               | 15.0       | 
 | 25               | 25                | 4               | 12.7       | 
| 20               | 20                | 3               | 10.9       | 

### How to choose good one?
Unfortunately, there is no absolutely reliable way to determine the internal components of a motor 
without disassembling it. Motors with the same pattern on the front 
may have different internal structures, 
while motors with completely different external appearances could be similar inside.

The only approximate method to guess motor internals - is .... the motor weight!
<img src="../../assets/images/on_scales.jpg">

Because more powerful motors have more metal inside their weight should be higher
Internals and power guess by weigh:
- 30mm magnets/stator - 2.9 kg
- 25mm magnets/stator - 2.6 kg
- 20mm magnets/stator - 2.3 kg
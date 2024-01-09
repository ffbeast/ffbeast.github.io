---
layout: default
title: Encoders
parent: Common
grand_parent: EN
nav_order: 3
---

- TOC
{:toc}

---

## Supported encoder types

Currently firmware supports **incremental type of encoders only**.
Theoretically any incremental encoder will work. It could be optical, magnetic etc. Requirement - output by **A/B** impulses.

{: .important }
> **Z index is not used**, so it is not critical if encoder has it or not.

## What is PPR/CPR?

**PPR** - Pulses per rotation. Show how many pulses each channel (А or B) produces for one full rotation of encoder.

**CPR** - Counts per rotation. Shows how many position counts it is possible to calculate from encoder by combining two channel pulses from encoder

Relation: **CPR = 4 x PPR**

In encoder datasheet any of this values could be.
In scope of all following text CPR will be used. So if you see PPR in datasheet for your encoder just multiply it by 4 to get CPR.

## CPR requirements?

In general case firmware will work with any. But for usage in pare **with howeroard motor** my recommendation is 
to use **1000 CPR and more** when driving encoder directly from motor shaft without reduction.

If encoder will be connected with reducer encoder with lower resolution could be used.

{: .highlight-title }
>Example
>
>Encoder connected to the motor with reduction ratio 1:5. Minimum encoder CPR needed could be calculated as 1000/5 -> 200 CPR and more.

## Recommendations on purchase 

There are tones of encoder available on the market. Some of them are tested already and will definitely work. But no direct links will be there.
Those links become outdated quickly, so just use search :)  

### CUI - AMT 10x series
<img src="../../assets/images/AMT10x.png">

Most expensive, but most reliable option available. It has very compact form. It is represented with several options:

- AMT-102 (8192 CPR)
- AMT-103 (8192 CPR)
- **AMT-10E2 (20480 CPR)**
- **AMT-10E3 (20480 CPR)**

I prefer last two options for my devices. As them cost the same as first two, but have higher CPR.

{: .important }
> Those models have different form factor with connector output to the front and to the bottom. 
> Models which marking is ended with 2 are vertical. Models ending with 3 are with front connector.

### OMRON-style
<img src="../../assets/images/omron.jpg">

Countless variants are there. All of them are "clones" of OMRON encoder. Different CPR available. Just some model are:
- E6B2-CWZ5B
- E6C2-CWZ6C
- 38S6G5-B-G24N
- E6B2-CWZ1X
- YT06
- etc...

{: .important }
> **Check which power encoder require and if signal line needs pull-down/pull-up**.
>
> Not all encoders are equal and work from 5v. Some of them need 12v or even 24v to work.
> In addition those encoders could work in different mode for signal lines. Just check datasheet of encoder exact mode 
> of your encoder and if it requires pulling of signal lines to ground or power line.

### Magnetic encoders
<img src="../../assets/images/magnetic.png">

This group is common in principle of work. Usually it is a PCB with small chip on it. To make it work correctly it requires
a magnet carefully placed and centered on the motor shaft. PCB should be placed precisely to the magnet axis of rotation.
It is the cheapest option. But you need to have some imagination how to mount it on the motor. There is no single standard solution for it. 
Recommended options from this group:

- MT6701 (4096 CPR)
- MT6825 (16384 CPR)

{: .warning }
> **TLE5012B**.
>
>  TLE5012B (16384 CPR) encoders are not recommended. Those encoders have programmed "dead zone". As result when changing direction
> it add feel of some backlash and ruin experience of using force feedback. 
>  Just **choose another solution!**

{: .important }
> **Magnetic encoders are extremely sensitive to relative position to the magnet!**.
>
> Of axis magnet placement causes non linearity in calculated forces. Good article about it [**there**](https://www.akm.com/eu/en/products/rotation-angle-sensor/tutorial/angular-error/).
>
> So if you are not sure that you could mount encoder and magnet with good amount of precision - just **choose another solution!**


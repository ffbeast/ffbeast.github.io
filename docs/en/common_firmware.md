---
layout: default
title: Firmware flashing
parent: Common
grand_parent: EN
nav_order: 4
---

- TOC
{:toc}

---
## STM32CubeProgrammer 
To flash FFBeast firmware to controller you need to use 
[**STM32CubeProgrammer**](https://www.st.com/en/development-tools/stm32cubeprog.html#get-software). 
It is specialized util for flashing STM32 controllers.
Just download it from official site and install.

## External power

{: .important }
> ODrive boards do not power up from USB! 
> 
> **Connect external power source to boot the controller!**

## DFU
All STM32 controllers support firmware flashing in DFU(Device Firmware Upgrade) mode directly via USB cable. 
Most boards have physical switch that allow to enable boot in DFU state. Here are some examples.

### ODrive
<img src="../../assets/images/odrive_dfu.jpg" width="360">

Usually it have micro switch. So process of booting in DFU mode will be following:

- Connect board to PC via USB cable.
- Disconnect external power from the board.
- Turn micro switch to DFU position.
- Connect external power - controller will boot in DFU mode.
- [Flash firmware](https://ffbeast.github.io/docs/en/common_firmware.html#flashing-process).
- Disconnect external power.
- Turn micro switch to original position.
- Connect external power - controller will boot in normal mode.

### MKS XDrive
<img src="../../assets/images/mks_single_dfu.jpg" width="360">

This boards have jumper on it. So process of booting in DFU mode will be following:

- Connect board to PC via USB cable.
- Disconnect external power from the board.
- Remove DFU jumper.
- Connect external power - controller will boot in DFU mode.
- [Flash firmware](https://ffbeast.github.io/docs/en/common_firmware.html#flashing-process).
- Disconnect external power.
- Install DFU jumper.
- Connect external power - controller will boot in normal mode.

### ODESC 4.2
<img src="../../assets/images/odesc_42_dfu.jpg" width="360">

This boards do not have dedicated switch or jumper but have special button:

- Connect board to PC via USB cable.
- Connect external power. Controller will boot in normal mode.
- Press and hold **BOOT** button.
- Press **RESET** button - controller will reboot in DFU mode.
- [Flash firmware](https://ffbeast.github.io/docs/en/common_firmware.html#flashing-process).
- Press **RESET** button - controller will boot in normal mode.
 
## ST-LINK
Unfortunately not all boards available on market have physical DFU mode switch. In case it is missing on your board
you will need to use ST-LINK to flash firmware to the controller. This procedure requires an STLink/V2 or compatible programmer.

To use ST-LINK follow the procedure:
- Wire ST-LINK to ODrive board. You need GND, SWD, SWC and NRST pins connected. 
- Connect ST-LINK to PC via USB cable.
- Connect external power to controller. It will be ready for flashing.
- [Flash firmware](https://ffbeast.github.io/docs/en/common_firmware.html#flashing-process).
- Disconnect external power.
- Disconnect ST-LINK.
- Connect external power - controller will boot in normal mode. 

{: .important }
> Unfortunately not any ST-LINK will work :(. 
> There are multiple reports and topics that cheaper ST-LINK clones often non reliable and do not 
> perform stable communication with STM32 controller. Nobody is protected from it. 
> If you can - try to buy controller with possibility to enable DFU mode physically or ST-LINK from trusted source.


## Flashing process
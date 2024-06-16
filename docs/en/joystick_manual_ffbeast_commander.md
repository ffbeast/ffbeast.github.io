---
layout: default
parent: Flight Controls Manuals
title: FFBeast Commander
nav_order: 3
---

- TOC
{:toc}

---
# Generic functionality
Interface of program is divided in several sections representing logical parts of functionality.   
<img src="../../assets/images/manual/commander_ui_blocks.jpg" width="720">

## Device state
It is part of the UI which outputs some helpful information

**Enable automatic profile activation** - Do what it says. If last selected profile is active no mater which game and flight module is detected 

**Joystick/Rudder connection states** - Shows if device is connected and version of firmware running on device

**Telemetry data source** - Shows game detected by software and providing telemetry

**Flight module** - Shows flight module name detected by software. Automatic profile switching is based on this name

**Yaw/Pitch/Roll** - Physical position of axis reported by device

## Profiles
Profile section allows to save effect profiles and then autoload them when game and flight module detected or select them manually.

In order to create a profile which can be automatically selected when flight module is detected:
- Select game from dropdown list.
- Input flight module name (just copy paste it from **Flight module** field when mission is running)
- Save profile.

Next time game will be running with that module and  **Enable automatic profile activation** checkbox is selected - profile will be activated automatically.

{: .important }
> **Important!**
> 
> Profile with same game selected, same flight module and same profile comment **will be overwritten** when saved.
> you can make several profiles for single flight module by alternating profile comment. 
> 
> **First profile in list matching criteria will be automatically selected when module detected.**

## Telemetry
This section has dual functionality. 

- Output generic telemetry data received by software. 
- Emulate telemetry data for effect testing purpose.

To start telemetry emulation just switch **Enable telemetry data override** checkbox and move sliders to desired values. 

{: .important }
> **Important!**
>
> Only common telemetry data is output there and can be emulated. Game/module specific data is not available for emulating!

## Effects


# Game support 
## DCS
## Il-2
## MSFS
## Condor 2
## War Thunder

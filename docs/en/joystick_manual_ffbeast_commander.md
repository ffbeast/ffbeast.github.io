---
layout: default
parent: Flight Controls Manuals
title: FFBeast Commander
nav_order: 2
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

In order to create a profile which can be automatically selected when flight module is detected you need:
- Select game from dropdown list.
- Input flight module name (just copy paste it from **Flight module** field when mission is running)
- Save profile.

Next time game will be running with that module and  **Enable automatic profile activation** is selected profile will be activated automatically

## Effects
## Telemetry override

# Game support 
## DCS
## Il-2
## MSFS
## Condor 2
## War Thunder

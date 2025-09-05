---
layout: default
title: Flight controls
parent: Downloads
nav_order: 1
---

{: .important }
> Check up to date documentation for [**FFBeast Setup**](ffbeast_setup.html) and [**FFBeast Commander.**](ffbeast_commander.html)

{: .important }
> Check [**effect profiles page**](downloads_effect_profiles.html) for profiles compatible with current version.

[//]: # (### Firmware update procedure)

[//]: # (<iframe width="560" height="315" src="https://www.youtube.com/embed/tf08TGMFgdo?si=JhXzllNthwEHj5nG" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>)

### Release candidate
- [**RC.25.1.3.Full**](../../assets/firmware/ffbeast-flight-controls-RC.25.1.3.Full.zip) (Software + Firmware)
  - MOZA grip support.
  - VPC UH-60 grip support.
  - VPC VFX analog axes fix.
  - DCS periodic effects fix
  - MSFS telemetry fix for missing flaps, gear, afterburner and spoilers data.
  - Fix commander stutter when MSFS telemetry selected
  - il-2 module recognition
  - il-2 gunfire effect in telemetry
  - Warthunder flight module recognition
  - Warthunder periodic effect fixes (overspeed, overG, stall. Commander need to be running with Warthunder telemetry selected).
  - Fix main rotor frequency multiplier was not saving
  - New dynamic motion range effect added (check [**effect documentation**](ffbeast_commander_effects.html#dynamic-motion-range))
  - Matching flight modules by part of the name
  - Analog axis hardware trim support
  - Assigning trim buttons on button state change instead of just on pressed state. Will not catch constantly pressed buttons automatically any more.
  - Hardware trim smoothing
  - Hardware trim profiles
  - Automatic dead zones calibration of analog axes connected to ODrive.
  
### Release candidate
- [**RC.25.1.2.Patch**](../../assets/firmware/ffbeast-flight-controls-RC.25.1.2.Patch.zip) (Software + Firmware)
  - Fix DCS DirectX constantly pulling to the side.
  - Fix for VPC Alpha analog axes.
  - Small fix for MSFS telemetry(should eliminate random Commander closing).

{: .note-title }
> **Update from previous version process**
> - Flash new firmware on top of previous version **WITHOUT ERASING!** All hardware settings will remain unchanged.
> - Unzip files from archive to previous version install folder.
> - Run RC.25.1.2 exe files to use new version.

### Release candidate
- [**RC.25.1.1.Full**](../../assets/firmware/ffbeast-flight-controls-RC.25.1.1.Full.zip) (Software + Firmware)
  - Fix for Condor 2 periodic effects (stall, flutter, etc).
  - Fix for il-2 periodic effects (stall, gunfire, etc).
  - Fix of XPlane plugin (require setup update in Commander).
  - Fix for Elevator Weight effect.
  - SimConnect library updated to the latest version (for MSFS telemetry).

{: .note-title }
> **Update from previous version process**
> - Flash new firmware on top of previous version **WITHOUT ERASING!** All hardware settings will remain unchanged.
> - Backup **config.ini** file from ui folder in case you want to keep Commander settings unchanged.
> - Unzip files from archive to previous version install folder **WITH OVERWRITING** of older files.
> - Restore **config.ini** file from backup.
> - Run RC.25.1.1 exe files to use new version. 

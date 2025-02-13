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

### Release candidate
- [**RC.24.1.5.Patch**](../../assets/firmware/ffbeast-flight-controls-RC.24.1.5.Patch.zip) (Software + Firmware)
   - Improved curve editor with possibility to generate the most used curves.
   - Improved logic of scaling effects for different devices (check "[**Max force available**](ffbeast_setup_effects.html#max-force-available-flight-controls-only)" page for details how it works now).
   - Added [**Local AoA**](ffbeast_commander_effects.html#local-aoa) effect.
   - Fix for SPI and GPIO not works in [**Hardware test mode**](ffbeast_setup_license.html#hardware-test-mode-flight-controls-only).
   - Fix for DCS telemetry translating high AoA and G effects when on ground, triggering AoA and G shakers.

{: .note-title }
> **What is a Patch?**
>
> - **Patch** is the type of archive, which contains only files that need to be updated.
> - **Patch** need to be put into the folder where most recent **Full** version is installed.
> - If you do not have **Full** version installed yet you need to download it and install.
> - **Patch** always changes only the last number in the version.
> - You need to use **Patch** on top of **Full** version with matching first two numbers.
>
> {: .opaque }
> <div markdown="block">
> {: .highlight-title}
> > Example
> > - The latest version for download is **24.1.5.Patch**. 
> > - No previous **24.1.X** versions installed.
> > - Navigate in the list the most recent archive with name **24.1.X.Full**.
> > - Download and install it.
> > - Put all new files from **24.1.5.Patch** version into resulting folder.
> > - Update firmware to the version containing in **24.1.5.Patch** archive.
> > - Use new version of **FFBeast Setup** and **FFBeast Commander** to interact with devices.
> </div>


### Release candidate
- [**RC.24.1.4.Full**](../../assets/firmware/ffbeast-flight-controls-RC.24.1.4.Full.zip) (Software + Firmware)
  - **Starting from this version flight controls software/firmware ecosystem is separate from wheel firmware/software. All further updates will be separate for both ecosystems.**
  - **Firmware changes:**
    - Hardware test mode added when activated without a license key.
    - New integrated spring effect is added. It emulates centering forces in games without FFB.
    - Support for VPC grips (FLNKR, Alpha, Alpha Prime, MongoosT, VXF).
    - Support for TIANHANG F18 grip.
  - **Software changes:**
    - Totally reworked system of effects, with many of new effects added. 
    - Hardware trim and force release assignable on any joystick button.
    - Game configuration from inside the commander app.
    - XPlane support.
    - Notification of new versions with possibility to skip.

## Legacy versions

### Release

- **240719**
    - [**240719.Software**](../../assets/firmware/ffbeast-software-240719.zip) (Software only)
    - [**240719.Firmware**](../../assets/firmware/ffbeast-firmware-240719.zip) (Firmware only)
    
 
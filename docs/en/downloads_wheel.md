---
layout: default
title: Wheel
parent: Downloads
nav_order: 3
---

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
- [**RC.24.1.5.Patch**](../../assets/firmware/ffbeast-wheel-RC.24.1.5.Patch.zip) (Software + Firmware)
  - Dynamic dampening settings returned to PRO version.
  - Communication library and code example added for easier understanding and use of  [**custom USB communication protocol**](wheel_programming.html). Check **_ffbeast-wheel-api-example-app_** folder in archive.

### Release candidate
- [**RC.24.1.4.Full**](../../assets/firmware/ffbeast-wheel-RC.24.1.4.Full.zip) (Software + Firmware)
  - Starting from this version wheel software/firmware ecosystem is separate from flight controls. No need to switch firmware into **Wheel** mode. After firmware flashing device will be immediately recognized as **FFB Wheel device**.
  - New **Integrated spring** is added. It emulates centering forces in games without FFB.
  - **Reset center** button added for wheel centering from UI.
  - [**Custom USB communication protocol**](wheel_programming.html) added for controlling device from additional software without usage of DirectX FFB protocol.

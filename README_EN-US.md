<div align="center">
  
  # Windows CE Emulator Collections
  Windows CE Emulator Collection Based on Windows PE<br /><br />
  中文说明：https://github.com/WinPad1993/Windows_CE_Emulator_Collections/blob/main/README.md
  
</div>


## What are CE Emulator Collections <br />
When Microsoft developed Windows CE 1.0 to Windows CE 3.0, in order to facilitate developers to directly test their WinCE Apps on their own computers, some Windows CE (or CE-based operating systems, such as Windows Pocket PC 2000, etc.) SDKs came with Shell emulators that can run on Windows NT. However, with the continuous development of the Windows NT family, Windows' compatibility with these emulators has become increasingly poor (for example, in Windows 11, the installation programs of these versions of the SDK can no longer be started), and even completely lost support for emulators (such as the Windows Pocket PC 2000 emulator). Therefore, in order to facilitate the operation of these emulators, this collection was created with the help of Windows PE.
<br />

## How to use it
Since this image is based on Windows PE (Windows 2000, FLP kernel), it can be directly mounted into the virtual machine. The selection menu will automatically start after the boot is complete. Just enter the number according to the prompt on the menu to start the simulator you want. 
**Note: This image requires the virtual machine to have 700MB of memory and does not require a hard disk image!** <br />
### CEEC Configuration Notice – Tips for Successful Emulation

**By HAWEEN CHEN**  
*9th April 2026*

First of all, a big thank you to **ONEW STUDIO** for the **CEEC (Windows CE Emulator Collections)** project. It's a fantastic initiative for exploring and preserving the Windows CE environment on modern PC hardware.

During my recent deployment, I encountered a few configuration hurdles that I managed to troubleshoot and resolve. I wanted to leave this comment to document those findings in the hope that they help other users avoid the same pitfalls.

#### 🔧 Configuration Hints & Troubleshooting

**1. Hypervisor Compatibility: Use VirtualBox instead of VMware**
Due to specific display driver and mouse integration issues within the pre-installed environment (PE) stage of CEEC, **VMware Workstation/Player is not recommended** for this project. I experienced significant cursor misalignment and graphical glitches. Switching the VM to **Oracle VirtualBox** resolved these input and display issues completely.

**2. Virtual Optical Drive Configuration (CRITICAL)**
This is the most common cause of the *"Path Not Found"* error during setup. When configuring the virtual machine settings for CEEC:

- ❌ **DO NOT** use **ICH6**, **SATA**, or **AHCI** controllers for the virtual CD/DVD drive.
- ✅ **MUST** use a **IDE ** controller for the optical device.

Failure to set the optical drive to IDE mode **will** result in the emulator being unable to locate the system path, causing the boot process to halt immediately.

**3. Bootloader Drive Letter Limitation (D:\ Requirement)**
Due to a hard-coded limitation in the current bootloader version( 0.4.5 or lower ver.), the CEEC environment expects the content volume (whether it's a RAMDisk or iso file) to be mounted specifically at **`D:\`**. If the media is assigned any other drive letter even failed to connect, the loader will fail to find the required components and the emulation will not start.

- **For a Stable Experience,** It is strongly recommended **never unmount or eject** the virtual CD/DVD drive during the session.
- **For Quick Testing Only,** As an alternative fallback, you *can* attempt to run older CE versions (1.0 - 2.0) and some legacy emulator binaries within a **Windows 2000 or Windows XP** virtual machine environment even phycial machine **with out install any SDK and VB2005 component**. However, please be aware that the user experience and hardware compatibility in this fallback scenario are significantly inferior to the native CEEC environment.

---

CEEC is an excellent resource for diving into the legacy of Windows CE. While some quirks with the PE driver environment remain, I'm excited to see how this project evolves. Keep up the great work!

**HAWEEN CHEN**
```

## Here is the systems that can emulated
Green:Have been added and can work with few problems.<br />
Azure:Have been added but have some problems.<br />
Yellow:Haven't been added because of some problems.<br />
Red:Haven't been added because of missing of files.<br />
Black:Maybe won't be added.<br />
![111-2](https://github.com/user-attachments/assets/78e612cb-97c1-4c6d-afc8-6ee731a1eaf6)
<br />


## Specially thanks

1.All of the members of the ONEW Studio<br />

<table>
  <tr>
    <td align="center"><a href="https://space.bilibili.com/484165196"><img src="https://github.com/Inter1006/Extensions/blob/main/1720663857759dcbe7c89c6455282b29bc8695211ad7924a0.jpg" width="150px;" alt=""/><br /><sub><b>351<br />351Workshop</b></sub></a><br /></td>
    <td align="center"><a href="https://space.bilibili.com/1756824708"><img src="https://github.com/Inter1006/PenPointOS_Vbox/blob/Readme_Files/b_fa517952f054ca8c99a234cc1b50b50b.jpg" width="150px;" alt=""/><br /><sub><b>Inter1006<br />INTER_INIT</b></sub></a><br /></td>
    <td align="center"><a href="https://space.bilibili.com/410046866"><img src="https://github.com/Inter1006/Extensions/blob/main/1720663903084330ee6855a3795b453f2ab6ded4863c9b08a.jpg" width="150px;" alt=""/><br /><sub><b>GoldApple<br />不务正业的金苹果</b></sub></a><br /></td>
    <td align="center"><a href="https://space.bilibili.com/648710692"><img src="https://avatars.githubusercontent.com/u/109840619?s=400&u=8c905a3d85482006220ae0074e8c36e3fc5729eb&v=4" width="150px;" alt=""/><br /><sub><b>WinPad(御坂)<br />MisakaMikoto1122</b></sub></a><br /></td>
    <td align="center"><a href="https://space.bilibili.com/2057331843"><img src="https://github.com/Inter1006/Extensions/blob/main/17206639278647b179c13f807cbc2bf27b899725d34fc5c79.jpg" width="150px;" alt=""/><br /><sub><b>DZY<br />DZY20070614</b></sub></a><br /></td>
    <td align="center"><a href="https://space.bilibili.com/437201853"><img src="https://github.com/Inter1006/Extensions/blob/main/1720663947047a3c221d7c72c685e35b27b3fe6d41b6f8f93.jpg" width="150px;" alt=""/><br /><sub><b>Zesa<br />LinuxMEMZ</b></sub></a><br /></td>
  </tr>
  
</table>
<br />
ONEW Studio QQ group：981893945 Welcome<br /><br />

## 其他

All of the Windows CE Emulators are from SDK created by Microsoft

## Friends

WindowsNT351's CE Collections：https://github.com/WindowsNT351/CE-Collections <br />
Inter's Penpoint Emulator：https://github.com/Inter1006/PenPointOS_Vbox/tree/main <br />
Axium. yu's Minecraft Servers：https://www.sakuravalley.xyz <br />

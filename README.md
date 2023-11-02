# Asus X555QA/QG/Y Hackintosh (High Sierra 10.13.3 - 10.13.6)

![progress](https://img.shields.io/badge/Progress-to_fix_old_AMD_OSX-red.svg)
![3Dgraphics](https://img.shields.io/badge/3Dgraphics-not_working-red.svg)
[![periphericals](https://img.shields.io/badge/periphericals-partial_working-orange.svg)](https://github.com/sebasrock156/Asus-X555QA-Hackintosh#works)
![installation](https://img.shields.io/badge/installation-working-green.svg)


**Let's go with my hardware**:
---

Hardware | Model
--- |:--:
![processor](https://i.imgur.com/H44zEoW.png) | AMD A10 9620P, 4 cores/threads@3,0Ghz
![igpu](https://i.imgur.com/7TZmF2e.png)| Radeon R5 512MB VRAM @800Mhz (Not supported)
![audio](https://i.imgur.com/SCKuD0b.png) | Conexant CX20752
![dgpu](https://i.imgur.com/7TZmF2e.png) | (Not available)
![wlan](https://i.imgur.com/dUwPhAC.png) | Realtek RTL8821AE+Bluetooth 4.0 (Not supported)
Ethernet | Realtek RTL8111
![ddr4](https://i.imgur.com/g3gLTem.png) | Samsung 8GB CL22@2133Mhz (in-build) + Crucial 8GB CL19@2400Mhz (external)
![ssd](https://i.imgur.com/Jixm0UG.png) | Crucial BX500 SSD 480GB (TLC SM2258XT Controller)
---

<details>
 
**Now, some minimum hardware recommendations**:

---

Hardware | Model
--- |:--:
RAM | Any Samsung, Hynix or Kingston DDR3 8GB(4GBx2).
Audio Card | Any Realtek Audio Card (some Broadcom cards may not work).
WLAN Card | Any Intel network card (A few Realtek cards works externally; Intel supported cards is listed below).
SATA Drive	| Any Solid State Drive (SSD) with 240GB of storage.
IDE Drive | Add a caddy for SATA Output, then, I recommend any Hard Disk with 500GB/1000GB of storage.
---
 
</details>

## Works：

<details>

Native Screen (1366x768) ✅
  
RJ45 Ethernet Connection ✅

Touchpad (Partial works, gestures are broken) ✅ 

Camera (althrough is awful) ✅

Battery Stats & Charge level (But for ACPI modifications, may have some of battery drain) ✅ 


## Not work (IDK how to fix it at all):

Integrated Graphics (3D Acceleration is broken, use default VESA drivers) ❌

Multi Screen (VESA doesn't support multi-screen) ❌

HDMI (No graphic drivers) ❌ 

VGA (No graphic drivers) ❌

Screen Backlit (This may be fix with some SSDT, but if 3DGfx doesn't work...) ❌

Audio Card ❌ (It's partially work via audio jack, but soundspeakers doesn't work).

Hibernate ❌ (It's full broken)
 
Bluetooth ❌ (It's broken with Realtek):

Wi-Fi ❌ (It's broken with Realtek):

Card Reader ❌ (ACPI Problems, I'll trying to fix for Monterey release)

</details>

## Installation Method:
<details>

**Before to try it**:

Maybe you need a External Keyboard and Mouse for use, and evite use USB 3.0/3.1 for Bootable USB Drive.

1. Using any macOS BigSur Image based on Olarila project and Balena Ecther for doing Booteable USB Drive.

2. If macOS image won't boot, mount Booteable USB Drive ESP (EFI) partition with ESP Mounter Pro or Clover/OpenCore Configurator (MacOS) or MiniTool Partition (Windows) and replace EFI Folder with THIS repo EFI Folder.

3. Boot to USB Drive always with BIOS Secure Boot ENABLED (if you disable Secure Boot, MacOS Preinstalled on Hard Drive/Solid Drive never will boot, stuck on Apple logo). 

## Post-Installation：
 **WARNING ⚠️** : If you wanna have Dualboot with Windows or Linux, Touchpad may be don't work, OpenCore EFI modify some ACPI values (Advanced Configuration and Power Interface, a.k.a. memory access & Power from BIOS/Chipset to peripherics and motherboard components) and Touchpad (Synaptics or Elantech) crash with these modifies.

1. Mount the macOS Drive EFI Partition (with ESP Mounter Pro), later, drag EFI Folder from Booteable USB Drive and reboot.

2. Now, when you boot from your macOS Drive, go to Extras folder and run "GenSMBIOS.command", select option 2 for select included config.plist, after, select option 3 for generate a new Apple SMBIOS and Serial. This is for fix not working Apple ID and Apple Aplications.

3. If you have any Intel Wi-Fi card mentioned above, move and open "HeliPort" and configurate for enable in Autostart (System Preferences), Network connection aren't the best, but works.
</details>

## Applications Support:

**Warning**: Some Apple apps as iMessage, FaceTime, App Store, Apple Music and etc won't login although you have patched SMBIOS before, you need an Apple product serial compatible with Apple Support too, consult in Olarila how fix it.


## Misc:
This is based on OSX AMD dmg files.

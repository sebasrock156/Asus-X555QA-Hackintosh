# Asus X555QA/QG/Y Hackintosh (High Sierra 10.13.3 - 10.13.6)

![progress](https://img.shields.io/badge/Progress-to_fix_old_AMD_OSX-red.svg)
![3Dgraphics](https://img.shields.io/badge/3Dgraphics-not_working-red.svg)
[![periphericals](https://img.shields.io/badge/periphericals-partial_working-orange.svg)](https://github.com/sebasrock156/Asus-X555QA-Hackintosh/tree/High-Sierra#works)
![installation](https://img.shields.io/badge/installation-working-green.svg)
[![Intel OSX](https://img.shields.io/badge/HackintoshIntel-available_here-violet.svg)](https://github.com/sebasrock156/Acer-E5-572-TMP246-OpenCore)


![banner](https://i.imgur.com/8QrfTIX.png)

**Let's go with my hardware**:
---

Hardware | Model
--- |:--:
![processor](https://i.imgur.com/H44zEoW.png) | AMD A10 9620P/A12 9700P/FX 9800P, 4 cores/threads@3,0/3,4/3,6Ghz
![igpu](https://i.imgur.com/7TZmF2e.png)| Radeon R5/R7 512MB/1GB VRAM@720/758Mhz (Not supported)
![audio](https://i.imgur.com/SCKuD0b.png) | Conexant CX20752
![dgpu](https://i.imgur.com/7TZmF2e.png) | (Not available, try to replace for any MB with some Radeon dGPU)
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
RAM | Any Samsung, Crucial or Kingston DDR4 8GB (in-unique slot).
Audio Card | Any Realtek and some Conexant Audio Cards.
WLAN Card | Any Intel network card, some Broadcom network cards, and few Qualcomm/Atheros network cards).
SATA Drive	| Any Solid State Drive (SSD) with 240GB or more of storage.
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
 
Bluetooth ❌ (It's broken with Realtek and Qualcomm, replace it for an Intel Wireless mini PCI-E card)

Wi-Fi ❌ (It's broken with Realtek I'll try replace for an Intel Card in future)

Card Reader ❌ (ACPI Problems, I'll trying to fix for newer releases)

</details>

## Installation Method:
<details>

**Before to try it**:

Maybe you need a External Keyboard and Mouse for use, and evite use USB 3.0/3.1 for Bootable USB Drive, if installation boot shows a 🚫 symbol, try putting the USB Pendrive in another USB Port.

1. Using any macOS Image based on Olarila project or AMD-OSX and Balena Ecther for doing Booteable USB Drive.

2. If macOS image won't boot, mount Booteable USB Drive ESP (EFI) partition with ESP Mounter Pro or Clover/OpenCore Configurator (MacOS) or MiniTool Partition (Windows) and replace EFI Folder with THIS repo EFI Folder.

3. Boot to USB Drive always with BIOS Secure Boot ENABLED (if you disable Secure Boot, MacOS Preinstalled on Hard Drive/Solid Drive never will boot, stuck on Apple logo). 

## Post-Installation：
 **WARNING ⚠️** : ACPI values (Advanced Configuration and Power Interface, a.k.a. memory access & Power from BIOS/Chipset to peripherics and motherboard components) could be changed with a macOS installation, if you do want make a Dualboot installation, some hardware periphericals might not work on Windows/Linux/Android.

If you have a ELANTECH Touchpad, this might not work on macOS, Apple kexts (drivers) usually doesn't detect Elantech devices; if you have been modified the BIOS Image (using AMFIBIOS tools), could do that Windows recognise the Touchpad as a SYNAPTICS device (is a bug from BIOS microcode in 320 version), in that case, touchpad might works. 

1. Mount the macOS Drive EFI Partition (with ESP Mounter Pro), later, drag EFI Folder from Booteable USB Drive and reboot.

2. Now, when you boot from your macOS Drive, go to Extras folder and run "GenSMBIOS.command", select option 2 for select included config.plist, after, select option 3 for generate a new Apple SMBIOS and Serial. This is for fix not working Apple ID and Apple Aplications.

3. If you have any Intel Wi-Fi card mentioned above, move and open "HeliPort" and configurate for enable in Autostart (System Preferences), Network connection aren't the best, but works.
</details>

## Applications Support:

**Warning**: Some Apple apps as iMessage, FaceTime, App Store, Apple Music and etc won't login although you have patched SMBIOS before, you need an Apple product serial compatible with Apple Support too, consult in Olarila how fix it.


## Misc:
This is based on OSX AMD dmg files.
In future, I'll try use Opencore for newer versions.

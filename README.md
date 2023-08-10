

Z77MX-QUO-AOS
=============

This page is dedicated to sharing information on installing OS X on your new [Z77MX-QUO-AOS](https://web.archive.org/web/20220529043445/http://quocomputer.com/shop/z77mx-quo-aos/) motherboard!

Contents
--------

*   [1 Recommended Hardware](#Recommended_Hardware)
*   [2 Notes on Geforce 7XX](#Notes_on_Geforce_7XX)
    *   [2.1 WINDOWS](#WINDOWS)
    *   [2.2 OS X/LINUX](#OS_X.2FLINUX)
*   [3 Firmware](#Firmware)
*   [4 Downloads](#Downloads)
*   [5 Settings](#Settings)
*   [6 Installation Guide](#Installation_Guide)
*   [7 Fixing iMessage/Back to mac](#Fixing_iMessage.2FBack_to_mac)
*   [8 Ozmosis H3C.1479](#Ozmosis_H3C.1479)
*   [9 Misc](#Misc)
*   [10 Credits](#Credits)

Recommended Hardware
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   Processor (i5 or i7 with HD4000)
    *   i5-3570K
    *   i7-3770S
    *   i7-3770K

*   Memory
    *   240-Pin DDR3 SDRAM DDR3 1600 (PC3 12800)

*   Graphics Cards
    *   GeForce 670
    *   GeForce 560 Ti
    *   ATI 5770 Vaper-X (HDMI Works out of box with 828m Bios)
    *   Geforce 650 Ti

Notes on Geforce 7XX
---------------------

(From the OZ): Check your 7xx GFX for full compatibility per your OS

7xx installation with IGPU (Integrated Graphics) Enabled:

WINDOWS

*   Install Windows with 7xx GFX card first
*   Install nVidia drivers
*   Shutdwon, Remove Card
*   Reboot to Windows with monitor connected to one of IGPU ports.
*   Install IGPU drivers
*   Reboot to BIOS
*   BIOS Features > Display Boot Option ROM Control to UEFI only
*   Peripherals > Init Display First to AUTO
*   Peripherals > Integrated Graphics to Enabled
*   Save and Exit
*   Shutdown and now install 7xx GFX

OS X/LINUX

*   Remove 7xx GFX
*   Reboot to BIOS
*   BIOS Features > Display Boot Option ROM Control to UEFI only
*   Peripherals > Init Display First to IGPU
*   Peripherals > Integrated Graphics to Enabled
*   Save and Exit
*   Shutdown and now install 7xx GFX

 Firmware
-----------

*   [Official](https://web.archive.org/web/20220529043445/http://quocomputer.com/projectq/technical/)
    *   [F3A Mirror](https://web.archive.org/web/20220529043445/https://www.dropbox.com/s/1z82t4kupg1hbo9/Z77MXQUOAOS.F3A) (7/17/13)
    *   [F2N Mirror](https://web.archive.org/web/20220529043445/https://www.dropbox.com/s/9ts0oeet0xhemsx/Z77MXQUOAOS.F2N) (7/5/13)
*   [Third Party GitHub Repo](https://web.archive.org/web/20220529043445/https://github.com/tuxuser/OzmosisBIOS)
*   [Third Party](https://web.archive.org/web/20220529043445/https://mrq7bqbfgwmjzd5m.tor2web.org/) (Supports Vanilla OS X installation)
    *   [H20.167X-MASS](https://web.archive.org/web/20220529043445/https://pastebin.com/38G6mkSA)
    *   [H2N.OZ1669M Mirror](https://web.archive.org/web/20220529043445/https://drive.google.com/uc?id=0B_sTfBTpTiGwb3J6cXJHUmxiY2c)
        *   Fixed All reported bugs
        *   Added RAID and El Capitan support
        *   Updated CPU MicroCode SandyBridge 6A7-29/IvyBridge 6A9-1B
        *   Updated OROM/EFI IRST RAID for SATA - v14.6.0.2285
        *   Updated EFI GOP Driver IvyBridge - 3.0.1027 / SandyBridge - 2.0.1024
        *   Updated HermitShell with SETVAR application/fixed BCFG application
    *   [H3C.1479 Mirror](https://web.archive.org/web/20220529043445/https://www.dropbox.com/s/up7o5kti7r238lm/Z77MXQUOAOS.H3C.1479.ROM)
        *   Added ASM1062 controller driver support (It can be found on various PCIe and Thunderbolt SATA adapters)
        *   Added LpcSensors/CpuSensors/GpuSensors version 6.0.1290.
        *   Added OpalSecurity support(needs testing)
        *   Added VoodooHdaKext Version 2.8.6 r98m(with fixed AC3/Encoded Digital).
        *   Removed ExtFs driver.
        *   Replaced CsmVideo with HermitCrabsLab version, allows better resolution(up to 2560x1440 tested) for non UEFI VBIOS graphic cards.
        *   Replaced SmcEmulatorKext with version 6.0.1290.
        *   Set BIOS Features/Display Boot Option ROM Control to Legacy Only by default(Legacy Only on Failsafe).
        *   Set(Back) BIOS Features/Intel Virtualization Technology for Direct I/O to Enabled by default(Enabled on Failsafe).
        *   Updated ACPI USB and Wifi support.
        *   Updated AHCI drivers with latest from AMI.
        *   Updated Intel RSTe SATA ROM and UEFI driver to V13.1.0.2030
    *   [H3B.894M Mirror](https://web.archive.org/web/20220529043445/https://www.dropbox.com/s/73byjb5ztr3qc6x/Z77MXQUOAOS.H3B.894M.ROM)
        *   Refactored nVidia device injector, added HDMI/DP audio support.
        *   Set BIOS Features/Display Boot Option ROM Control to Legacy only by default.
        *   Set BIOS Features/Boot Mode Selection to UEFI only by default.
        *   Restored "Windows Boot Manager" detection to fix Startup Disk preference pane selection.
        *   Ensure 'MLB' variable >= 17 digits, pad BaseBoardSerial with digits generated from UUID when needed.
    *   [H3A.828M Mirror](https://web.archive.org/web/20220529043445/https://www.dropbox.com/s/ql4mgidpke9cy3y/Z77MXQUOAOS.H3A.828M.ROM)
        *   Changed IGPU Fixed Memory Size from 64M to 32M to match the framebuffer.
        *   Changed TB PCIe Cache-Line Size from 32 to 64
        *   Use subsystemid when custom framebuffer for ATI cards is chosen.
        *   Disable nVidia device injection only on GTX 6/7 cards.
        *   Fix nVidia VBIOS version read on desktop ROMs
        *   Fix for nVidia cards when they are not posted
        *   Fix loading injector.kext from Fv.
    *   [H3A.820M Mirror](https://web.archive.org/web/20220529043445/https://www.dropbox.com/s/bb7hyn70h17q1nd/Z77MXQUOAOS.H3A.820M.ROM)
        *   Fix for Maverick installer. Update ATI Card List.
    *   [H3A.816M Mirror](https://web.archive.org/web/20220529043445/https://www.dropbox.com/s/4z7ksoeownqx3xe/Z77MXQUOAOS.H3A.816M.ROM)
        *   Fix loading SSDT table overrides.
    *   [H3A.801M Mirror](https://web.archive.org/web/20220529043445/https://www.dropbox.com/s/ermdt1xohguox3b/Z77MXQUOAOS.H3A.801M.ROM)
        *   10.8.5 audio distortion fixed.
    *   [H3A.739M Mirror](https://web.archive.org/web/20220529043445/https://www.dropbox.com/s/5we2v8t2s0f5qug/Z77MXQUOAOS.H3A.739M.ROM)
    *   [H3A.723M Mirror](https://web.archive.org/web/20220529043445/https://www.dropbox.com/s/da575evp5obzfnr/Z77MXQUOAOS.H3A.723M.ROM)

 Downloads
-

*   [Audio kext ALC892](https://web.archive.org/web/20220529043445/https://www.dropbox.com/s/t57f7ez8dq4zq3n/QUO%20Audio%20Update.pkg) (ONLY kext needed after vanilla install - Not required with H3C.1479 and above)
*   [QUO Legacy Package](https://web.archive.org/web/20220529043445/https://www.dropbox.com/s/agg3l19occmf50s/QUO_Legacy.08072013.zip)
*   [DarwinDumper](https://web.archive.org/web/20220529043445/https://bitbucket.org/blackosx/darwindumper/downloads) - Great for when we're trying to help you troubleshoot

 Settings
---------

*   BIOS: Recommended changes before Vanilla OS X Installation:
    *   Init Display: Integrated
    *   For thunderbolt: Set BIOS Features/Display Boot Option ROM Control to Legacy Only
*   Hardware
    *   Plug your SATA III (6 Gb/s) drives into either of the 2 white plugs, as the others will be at the SATA II (3 Gb/s) speed

 Installation Guide
-------------------

1.  Purchase a license of OS X and create a bootable USB image
2.  Install the latest third party firmware linked to above
3.  Make the BIOS changes referenced in the BIOS settings
4.  Press F12 on boot of your machine and select the bootable USB image
5.  Install OS X as usual
6.  After OS X boots, install the audio KEXT and re-boot (Not required with H3C.1479 and above)

Fixing iMessage/Back to mac
----------------------------

*   For some people iMessage will not function, this is due to the base board serial number not being 17 characters long. I would HIGHLY recommend installing [ChampList](https://web.archive.org/web/20220529043445/http://tools.inmac.org/) (SMBios tab) to generate a new serial number for a MacPro 3,1. Once you have it, you can set it like so:
    *   sudo nvram 4D1FDA02-38C7-4A6A-9CC6-4BCCA8B30102:SystemSerial=CK84593EXYL
*   Then set your baseboard serial number to be 17 characters, something like:
    *   sudo nvram 4D1FDA02-38C7-4A6A-9CC6-4BCCA8B30102:BaseBoardSerial=CK84593EXYL123456
*   Reboot + Profit. Some users have found that after rebooting removing the iMessage plist (~/Library/Preferences/com.apple.imservice.iMessage.plist) helps before attempting to sign in.

Ozmosis H3C.1479
-----------------

Upon first boot, Ozmosis will automatically create the ESP folder on first HDD with GUID partitioning scheme.

Folder structure

/EFI

/Oz (Defaults.plist, Theme.bin goes IN here)

/Acpi

/Load (DSDT and SSDT goes IN here)

/Dump (When ACPI DUMP mode bit is set thru nvram or Defaults.plist, ACPI Tables will be written here)

/Darwin

/Extensions

/Common (Kernel Extensions goes IN here)

[Start-up HotKeys](https://github.com/tuxuser/OzmosisBIOS/blob/master/README)

[List of NVRAM variables](https://github.com/tuxuser/OzmosisBIOS/blob/master/README)

Misc
----

For those dual booting with this board, please note that the third party firmware does not recognise/present nVidia's SLI option in the nVidia Control Panel on Win7 or Win8.1 with SLI capable GPUs. The official Firmware does support nVidia SLI.

To invoke the board's Backup Firmware (in case you brick it while flashing BIOS)

Method #1

1.  Turn off power via AC main switch on PSU.
2.  Press and hold the ATX power switch then switch the PSU back on while still holding ATX power switch. Hold the power button until the PC starts and shuts down again.
3.  Release the ATX Power switch, wait 5 secs and press it again. Backup Firmware should kick in. If not, repeat.

Method #2

1\. Shut your PC down 2. Hold the power AND the reset button for about 10 sec, then release. 3. Backup BIOS should kick in anytime soon now.

Credits
-------

[Original thread with referenced information](https://web.archive.org/web/20220529043445/http://www.insanelymac.com/forum/topic/285920-new-os-x-compatible-motherboard-quo)

[Ozmosis Github Repo](https://web.archive.org/web/20220529043445/https://github.com/tuxuser/OzmosisBIOS/blob/master/README)

[(Guide) Insert Ozmosis into UEFI BIOS](https://web.archive.org/web/20220529043445/http://www.insanelymac.com/forum/topic/301407-guide-insert-ozmosis-into-uefi-bios/?hl=+ozmosis)

Retrieved from "[http://wiki.osx86project.org/wiki/index.php?title=Z77MX-QUO-AOS&oldid=71163](https://web.archive.org/web/20220529043445/https://wiki.osx86project.org/wiki/index.php?title=Z77MX-QUO-AOS&oldid=71163)"

_  
This page was last modified on 24 August 2016, at 11:57.  
This page has been accessed 242,190 times.
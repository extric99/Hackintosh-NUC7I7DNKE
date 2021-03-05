# Hackintosh NUC7I7DNKE

## Verified working with 10.15.7 H2 and BigSur 11.2.2 Important read below when using Catalina.
![](https://github.com/extric99/Hackintosh-NUC7I7DNKE/blob/master/screenshot/Screenshot_BigSur.png)

## Configuration
- NUC: NUC7I7DNKE
- BIOS: 0069
- CPU: i7-8650U
- RAM: 2x 16GB G.Skill Ripjaws F4-2133C15S-16GRS 2133 MHz, DDR4
- Storage: m.2 WD GREEN 256GB
- dGPU: N/A
- WIFI/BT: Both the default intel BT module as DW1560 BT/wifi are supported by this built (use appropriate config.plist). It is advisable to replace the default module as the DW1560 will provide feature parity with a real Mac.

- SMIBIOS 8,1
- OpenCore 0.6.7

![](https://github.com/extric99/Hackintosh-NUC7I7DNKE/blob/master/screenshot/Screenshot_OC.png)

## Confirmed working
- Quick boot into MacOS and rock solid
- Wake Sleep
- Built-in Bluetooth (with default intel module, no Wifi)
- Wifi/Bluetooth/Unlock-Approve with Apple Watch (with DW1560)/Airdrop/Continuity
- Audio (No need to replug the HDMI cable thanks to the fake PCIID)
![](https://github.com/extric99/Hackintosh-NUC7I7DNKE/blob/master/screenshot/Screenshot_Audio.png)
- Sleep and Wake from mouse or keyboard
- Framebuffer for hardware acceleration (encoding/decoding/preview)

![](https://github.com/extric99/Hackintosh-NUC7I7DNKE/blob/master/screenshot/Screenshot_Hackintool.png)
![](https://github.com/extric99/Hackintosh-NUC7I7DNKE/blob/master/screenshot/Screenshot%20Framebuffer.png)


## Known Issues
- DRM issues that are inherent to integrated iGPU only
- Built-in wifi does not work. Since I replaced the wifi module I can not test the itwlm kext for intel wifi. If you need the intel wifi to work please add the kext yourself. [Download Intel Wifi kext here](https://github.com/OpenIntelWireless/itlwm)
- native SATA Support broken in BigSur but workaround is enabled in the config.plist. You can disable it if you have no SATA devices but only NVME.

## Bios Setup:

- Did not make any changes other than the boot order and fan profile

## USB Setup:

The 4 USB ports have been setup and configured as HS and SS. The bluetooth USB port as internal header.

## BigSur

SATA Support broken due to Apple dropping the AppleIntelPchSeriesAHCI class in AppleAHCIPort.kext. To workaround this, I added Catalina's patched AppleAHCIPort.kext with the MinKernel set to 20.0.0 as recommended by the OpenCore Install Guide. By default this is now enabled. To ensure that there are no issues with Catalina, please remove or disable the kext in the config.plist.


![](https://github.com/extric99/Hackintosh-NUC7I7DNKE/blob/master/screenshot/Screenshot_USB.png)

## Installation
1. Update the bios if needed
2. Open your config.plist and populate the Serial, Board Serial, UUID and MAC address.
Always use ProperTree for this!
3. Copy the folder to your EFI partition
4. Install (optional)
5. Go to System Preferences > Startup Disk and select your startup disk.
6. [Enable Trim](https://www.howtogeek.com/222077/how-to-enable-trim-for-third-party-ssds-on-mac-os-x/)
7. Done.

![](https://github.com/extric99/Hackintosh-NUC7I7DNKE/blob/master/screenshot/Screenshot_MAC.png)

## Credits

@RehabMan
@Leesureone for the initial version of the NUC OpenCore 5.9 EFI
visit [TonyMacx86 NUC7/8 Thread](https://www.tonymacx86.com/threads/guide-intel-nuc7-nuc8-using-clover-uefi-nuc7i7bxx-nuc8i7bxx-etc.261711/) for more info and discussion


## Tips
- Use [Hackintool](http://headsoft.com.au/download/mac/Hackintool.zip) to validate correct implementation of Framebuffer and USB
- Use [macinfo](https://github.com/acidanthera/MacInfoPkg) to generate your S/N
- Use [ProperTree](https://github.com/corpnewt/ProperTree) to edit config.plist

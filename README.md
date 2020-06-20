# Hackintosh NUC7I7DNKE

## Verified working with 10.15.5.
![](https://github.com/extric99/Hackintosh-NUC7I7DNKE/blob/master/screenshot/Screenshot_Info.png)

## Configuration
- NUC: NUC7I7DNKE
- BIOS: 0069
- CPU: i7-8650U 
- RAM: 1x 16GB G.Skill Ripjaws F4-2133C15S-16GRS 2133 MHz, DDR4
- Storage: m.2 WD GREEN 256GB 
- dGPU: N/A 
- WIFI/BT: Currently default Intel but Broadcom DW1560 on its way

- SMIBIOS 8,1
- OpenCore 5.9

![](https://github.com/extric99/Hackintosh-NUC7I7DNKE/blob/master/screenshot/Screenshot_OC.png)

## Confirmed working
- Quick boot into MacOS and rock solid
- Wake Sleep
- Built-in Bluetooth
- Audio
![](https://github.com/extric99/Hackintosh-NUC7I7DNKE/blob/master/screenshot/Screenshot_Audio.png)
- Sleep and Wake from mouse or keyboard
- Framebuffer for hardware acceleration (encoding/decoding/preview)

![](https://github.com/extric99/Hackintosh-NUC7I7DNKE/blob/master/screenshot/Screenshot_Hackintool_1.png)
![](https://github.com/extric99/Hackintosh-NUC7I7DNKE/blob/master/screenshot/Screenshot%20Framebuffer.png)


## Known Issues
- DRM issues that are inherent to integrated iGPU only
- Need to replace builtin wifi to get it working


## Bios Setup:

- Did not make any changes other than the boot order and fan profile

## USB Setup:

The 4 USB ports have been setup and configured as HS and SS. The bluetooth USB port as internal header. 


![](https://github.com/extric99/Hackintosh-NUC7I7DNKE/blob/master/screenshot/Screenshot_USB.png)

## Installation
1. Update the bios if needed
2. Open your config.plist and populate the Serial, Board Serial, UUID and MAC address. Always use ProperTree for this!
3. Copy the folder to your EFI partition 
4. Install (optional)
5. Go to System Preferences > Startup Disk and select your startup disk.
6. Done.

![](https://github.com/extric99/Hackintosh-NUC7I7DNKE/blob/master/screenshot/Screenshot_MAC.png)

## Credits

@RehabMan
@Leesureone for the initial version of the NUC OpenCore 5.9 EFI
visit [TonyMacx86 NUC7/8 Thread](https://www.tonymacx86.com/threads/guide-intel-nuc7-nuc8-using-clover-uefi-nuc7i7bxx-nuc8i7bxx-etc.261711/) for more info and discussion


## Tips
- Use [Hackintool](http://headsoft.com.au/download/mac/Hackintool.zip) to validate correct implementation of Framebuffer and USB
- Use [macinfo](https://github.com/acidanthera/MacInfoPkg) to generate your S/N
- Use [ProperTree](https://github.com/corpnewt/ProperTree) to edit config.plist

HW
1. MoBo - Gigabyte B560m Aorus Elite
2. Ram - Kingston HyperX Predator 4x8 3333mhz (3200 used profile)
3. Asus AMD Radeon RX 5500 XT DUAL EVO 8192MB 128bit 
4. Intel Core i5 10500(igpu off)
5. Samsung 970 evo nvme 512gb
6. BeQuiet 600w psu
7. no wifi/no bt card/stick (and dont have any kexts/patches, modify efi if you have one)

Tested: macOS Sequoia 15.7.3 
Work: 
Audio (DP, HDMI, 3.5jack) (with AppleALC)
GPU Acceleration 
Cable network (with lucy8125)
Nvme (with NVMEFix)
All usb (own UTBMap included, front panel work)
Front panel headphones out, back headphones out work
3.5 mics should work, but not tested (dont have one)
Imessage, AppStore, FaceTime - work


Must Have bios settings

```yaml
Bios: F10
Settings:
  Platform Power Management: 
    Erp: Disabled
    Native ASPM: Disabled
  Io:
    Internal Graphics: Disabled
    Audio Controller: Enabled
    Above 4G Decoding: DISABLED!!!!!!!! (cause video lags)
    SuperIO: All(one point) enabled
    USB Configuration: all enabled 
    Network, nvme - default
    Sata and RST Configuration:
      Sata mode selection: AHCI
  Misc:
    VT-d: disabled
    Trusted Computing:
      Security device support: Disable
Boot:
  CFG Lock: disabled
  Security options: System
  W10 features: Other OS
  CSM Support: Disabled
  Secure boot:
    Secure boot: disabled
```
OpenCore 1.0.7
Efi created with https://github.com/lzhoang2801/OpCore-Simplify (i think it's best tool for automated acpi patch + kext utility)
For manage serial keys use https://github.com/corpnewt/GenSMBIOS , iMac20,1
Please reset nvram after ANY CHANGES IN EFI (and before first install too)


Setup performed from usb3 back panel slot, from samsung t5 usb ssd.
MacOs install drive created from OpenCoreLegacyPatcher + MountEFI(copy EFI folder)
Dont use recovery installers, we have weak network stack in recovery, even your isp can provide above 100mbits, your dl speed is about 3-10 mbits with constant validations and stopping download.
Get mac or vmware macos and make usb install drive there

Im using 2 monitors
34 Xiaomi gaming curved monitor 3440x1440, 144hz
18 uperfect 1920x1080 120hz
all monitor's features work.

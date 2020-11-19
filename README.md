# Hackintosh your Deskmini310

## Configuration

| Specifications | Detail                                                                                    |
|----------------|-------------------------------------------------------------------------------------------|
| CPU            | INTEL I7-9700                                                                             |
| RAM            | 骇客神条 DDR4 2666MHz 8GB × 2                                                               |
| SSD            | WD SN750 500GB M.2 PCIE NVME                                                                  |
| WIFI/BT        | BCM94360CS2                                                                               |
| Cooler         | ID-COOLING IS40x                                                                          |

## BIOS

version：P4.4（support P3.x）

* Advanced
  * Chipset Configuration
    * Onboard HD Audio: Enabled
  * USB Configuration
    * XHCI Hand-off: Enabled
  * Super IO Configuration
    * Serial Port: Disabled  
  * CPU C State
    * CFG Lock: Disabled
* Security
  * Secure Boot: Disabled(by default)
* CSM Disable

默认情况下其他配置

## Works

* [x] 以太网/ WIFI /蓝牙/音频/ USB＆EX-USB /传感器

* [x] DP / HDMI双显示器输出

* [x] 关机、睡眠

## Notes

* 完成 macOS 安装 后 ([Installation Guide](https://www.tonymacx86.com/threads/unibeast-install-macos-mojave-on-any-supported-intel-based-pc.259381/)), 请打开 `config.plist` and  fill 填写 SMBIOS(PlatformInfo) info.

* ~~If you use `BCM94352Z` , please move BCM94352Z/* to CLOVER/kexts/Other.~~ （Unverified）

* 如果你需要 move CLOVER/kexts/Other/* 到 /L/E&/S/L/E, 请 modify `InjectKexts` to `Detect` in `config.plist` by Clover Configurator.

## Tips

* If you use `Chrome` , it is recommended to turn off `Chrome` completely when using `IGPU` operations(PS/FCP etc).[Chrome causing Final Cut Pro X to slow down, freeze, and crash](https://appleinsider.com/articles/19/06/20/chrome-causing-final-cut-pro-x-to-freeze-and-crash)

* 10.15.3 is the perfect version,if you have upgraded to 10.15.4, you need to add `igfxagdc=0` in the boot parameters to prevent the HDMI interface from being plugged in and out every time.
* ~~don't upgrade to 10.15.5 ,if you want to use hdmi~~（WEG 1.4.1 fix hdmi）
* 提高BIOS中的共享内存可以显着降低重新启动的可能性

## Why Hackintosh

Because We Can！

## Clover's Enlightenment Project

Thank [@liminghuang](https://github.com/liminghuang/asrock_deskmini310_hackintosh)

## ChangeLog

If there is an infinite reboot after upgrading efi, unplug the power and wait for a few seconds before powering up.

| Date      | Content                                                              |
|-----------|----------------------------------------------------------------------|
| 2019.7.28 | update clover  5018 & upgrade Mojave 10.14.6（Supplemental update has not been tested） , everything is alright |
| 2019.7.31 | update clover  5033                                                  |
| 2019.8.7  | upgrade Mojave 10.14.6 Supplemental update.(I reboot automatically several times after upgraded, and everything worked fine now) |
| 2019.8.11 | update clover  5045                                                  |
| 2019.8.27 | update clover  5058 & change FakeSmc to VirtualSmc & some Subtle changes |
| 2019.9.16 | update clover  5070 & some drivers & some kexts |
| 2019.10.10 | update some kexts  & upgrade macos catalina (I reboot & crash automatically several times after upgraded, and everything worked fine now)|
| 2019.10.16 | upgrade macos catalina 19A602 |
| 2019.10.21 | update clover 5096 & fix sleep wake |
| 2019.10.30 | update clover 5097 & upgrade macos catalina 10.15.1 |
| 2019.10.31 | update kexts & replace VoodooHDA to AppleALC |
| 2019.11.17 | update clover 5098 & use intelMausi.kext |
| 2019.12.10 | update clover 5100 & some kexts |
| 2019.12.12 | upgrade macos catalina 10.15.2 |
| 2020.02.28 | upgrade macos catalina 10.15.3 & update clover 5103 & some kexts |
| 2020.03.30 | upgrade macos catalina 10.15.4 & update clover 5107 & some kexts |
| 2020.06.15 | try opencore |
| 2020.07.18 | upgrade macos catalina 10.15.6 & update opencore 060 & some kexts(self-build (occasionally reboot When wireless sharing))|
| 2020.09.18 | update opencore 061 & some kexts , ready to upgrade big sur|
| 2020.09.25 | upgrade macos catalina 10.15.7|

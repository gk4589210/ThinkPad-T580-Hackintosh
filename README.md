# ThinkPad-T580-Hackintosh
# 中文版
# 联想ThinkPad T580上的macOS（本指南也适用于P52s i7-8550u，8250u理论上应该通用，不适用T480s）

此存储库包含10.14,10.15在Lenovo ThinkPad T580上运行macOS（目前为Mojave，Catalina ）的示例配置
--------------------------------------------------------------------------

机器配置表和驱动情况
---------
* 联想ThinkPad T580 【4k的UHD显示屏：3840x2160（京东方BOE NV156QUM-N44，非触摸）】

* 英特尔i7-8550U CPU

* 内存16GB RAM DDR4 2400-SODIMM

* 东芝Q200EX SSD+128G 东芝nvme联想跟机带

* 英特尔以太网I219-V4 有线网卡

* ~~Mac原装无线网卡bcm94360cs2（原装英特尔AC8265无法正常工作）~~

* ~~Wi-Fi设备芯片组为(0x14E4, 0x117) 显示Airport Extreme，使用AirportBrcmFixup.kext修改信道国家代码~~

* ~~蓝牙设备芯片组20702B0,固件版本:v150 c9318 免驱动~~

* 无线网卡改为DW1820A拆机卡（原装DELL拆机卡无需屏蔽针脚）

* 瑞昱Realtek ALC3287（“ALC257”）通过AppleALC.kext与layout-id：11，支持耳机和自带喇叭之间插拔自动切换。

* Intel UHD Graphics 620（禁用Nvidia MX150，macOS不支持Optimus）

* ACPI热修补电源管理和双电池状态

* SD卡读卡器走usb3.0通道，需要打开此USB端口即可使用

* Thunderbolt 3【BIOS里需要设置“Thunderbolt BIOS Assist”：Disable，“Security level” :No Security(允许自动连接 Thunderbolt 设备)。这样即可使前端类型USB type-c端口在macOS中工作，可以热插拔， DP / HDMI通过USB type-C：视频工作正常，连接扩展坞正常，雷电3设备工作正常，热插拔正常】

* 机器自带独立的HDMI端口：可以输出4k@30HZ到显示器。连接时会显示音频设备HDMI，并正常使用。

* 键盘Synaptics触摸板（PS / 2）使用ApplePS2SmartTouchPad.kext，EMlyDinEsH的v4.7b5，支持多点触控手势。
* 睡眠和唤醒正常

已禁用的设备和BIOS设置
-----------
* WWAN（无模块）
* TrackPad Synaptics指纹识别器无法驱动
* BIOS里设置Thunderbolt BIOS Assist为Disable(Enable雷电由BIOS控制决定，Disabled雷电由操作系统控制决定)，“Security level” :No Security(允许自动连接 Thunderbolt 设备和TYPEC)。
* BIOS里设置usb项Always on USB为enable，下面子项Charge in Battery Mode设置为enable（这样雷电口type-c就可以热插拔type-c外设）
* 关闭安全启动

UEFI BIOS固件修订
-----------
* BIOS版本 1.20,1.21,1.22通用


目前存在的问题
-------------
* 指纹无法驱动，触摸板还有缺陷。

备注
--------



# English
--------

# MacOS on Lenovo ThinkPad T580 (this guide also applies to P52s i7-8550u, 8250u should theoretically be universal, not T480s)

This repository contains 10.14,10.15 example configurations running macOS (currently Mojave, Catalina) on Lenovo ThinkPad T580
Machine configuration table and driving situation
--------------------------------------------------------------------------

Lenovo ThinkPad T580 [4k UHD display: 3840x2160 (BOE BOE NV156QUM-N44, non-touch)]
--------------------------------------------------------------------------
* Intel i7-8550U CPU

* 16GB RAM DDR4 2400-SODIMM

* Toshiba Q200EX SSD + 128G Toshiba NVMe Lenovo with strap

* Intel Ethernet I219-V4 wired network card

* ~~Mac original wireless network card bcm94360cs2 (original Intel AC8265 does not work properly)~~

* ~~Wi-Fi device chipset is (0x14E4, 0x117) Display Airport Extreme, use AirportBrcmFixup.kext to modify the channel country code~~

* ~~Bluetooth device chipset 20702B0, firmware version: v150 c9318 driver-free~~

* Wireless network card changed to DW1820A disassembly card (original DELL disassembly card does not require shielding pins)

* Realtek ALC3287 ("ALC257") supports AppleALC.kext and layout-id: 11, which supports automatic switching between the headset and the built-in speaker.

* Intel UHD Graphics 620 (Nvidia MX150 is disabled, macOS does not support Optimus)

* ACPI hot patch power management and dual battery status

* SD card reader uses usb3.0 channel, you need to open this USB port to use

* Thunderbolt 3 [Thunderbolt BIOS Assist needs to be set in the BIOS: Disable, "Security level": No Security (Allows automatic connection to Thunderbolt devices). In this way, the front-end USB type-c port can work in macOS and can be hot-plugged. DP / HDMI via USB type-C: the video works normally, the docking station is normal, the Thunderbolt 3 device works normally, and the hot-plug is normal

* The machine comes with a separate HDMI port: it can output 4k @ 30HZ to the display. When connected, the audio device HDMI is displayed and used normally.

* The keyboard Synaptics touchpad (PS / 2) uses ApplePS2SmartTouchPad.kext, EMlyDinEsH v4.7b5, and supports multi-touch gestures.

* Sleep and wake up normally


Disabled devices and BIOS settings
--------------------------------------------------------------------------
* WWAN (no module)
* TrackPad Synaptics fingerprint reader fails to drive
* Thunderbolt BIOS Assist is set to Disable in the BIOS (Enable is determined by BIOS control, Disabled is determined by operating system control), "Security level": No Security (Allows automatic connection of Thunderbolt devices and TYPEC).
* The USB item Always on USB is set to enable in the BIOS, and the following sub-item Charge in Battery Mode is set to enable (so that the Thunderbolt port type-c can hot-plug type-c peripherals)
* Turn off secure boot

UEFI BIOS firmware revision
--------------------------------------------------------------------------
* BIOS version 1.20, 1.21, 1.22 common

currently existing problems
--------------------------------------------------------------------------
* The fingerprint cannot be driven and the touchpad is defective.

Remark
--------------------------------------------------------------------------

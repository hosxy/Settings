VirtualBox 默认的设备产品型号貌似是 VirtualBox ，有时候想改下这个名字，然后发现图形界面好像没这个功能。然后到网上搜了一下，用命令行可以改，比如：
```
VBoxManage setextradata "<Your VM name>" "VBoxInternal/Devices/pcbios/0/Config/DmiSystemVendor" "Hasee"
VBoxManage setextradata "<Your VM name>" "VBoxInternal/Devices/pcbios/0/Config/DmiSystemProduct" "ThinZ7-CT5NA"
```
`DmiSystemProduct` 代表设备名称，`DmiSystemVendor`代表生产厂家名称

**Tips：最好在安装系统之前就改，我试过安装完 Windows 10 后再修改，虚拟机会没法启动，而修改后再安装则没问题，不知道是不是偶然，我也懒得求证了。**

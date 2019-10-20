VirtualBox 默认的设备产品名称是 VirtualBox ，有时候想改下这个名字，然后发现图形界面好像没这个功能。然后到网上搜了一下，用命令行可以改：
```
VBoxManage setextradata "<Your VM name>" "VBoxInternal/Devices/pcbios/0/Config/DmiSystemVendor"      "Compaq"
VBoxManage setextradata "<Your VM name>" "VBoxInternal/Devices/pcbios/0/Config/DmiSystemProduct"     "Thingamajig"
```
`DmiSystemProduct` 代表设备名称，`DmiSystemVendor`代表生产厂家名称

**Tips：最好在安装系统之前就改，我试过安装完 Windows 10 后再修改虚拟机会没法启动，而修改后再安装则没问题，不知道是不是偶然，我也懒得求证了。**

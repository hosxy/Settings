MS Office 2016及以后微软修改了安装程序，不能再自定义安装位置了，只能默认安装 C 盘。<br>
这里提供一个不修改注册表也能自定义安装位置的方法。其实就是创建一个符号链接将位于 C 盘的 MS Office安装目录链接到其他位置。

64 位 MS Office默认安装路径：`C:\Program Files\Microsoft Office` <br>
32 位 MS Office默认安装路径：`C:\Program Files (x86)\Microsoft Office`

**注：以下操作请在安装 MS Office 以前操作**

以安装 64 位的 MS Office 到`D:\Program Files\Microsoft Office`为例：
+ 在 `D:\Program Files\`下创建文件夹`Microsoft Office`
+ 以管理员身份运行一个 cmd(或者powershell) 窗口
+ 执行以下命令 `mklink /D "C:\Program Files\Microsoft Office" "D:\Program Files\Microsoft Office"`

然后正常安装 MS Office

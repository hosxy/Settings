众所周知，linux下的 alias 命令可以设置命令别名，异常好用。有时候在 Windows 下也有类似的需求，怎么办？<br>
其实 Windows 下也有一个命令可以做到这点：`doskey`，命令提示符窗口输入 `doskey /?`,可以查看帮助。
用法也很简单，和 `alias` 类似，比如：
```
doskey git=D:\MSYS2\usr\bin\git
```
而且它还可以传递命令行参数：
```
doskey git=D:\MSYS\usr\bin\git $*
```
更多用法，请查看帮助`doskey /?` <br>

但是有一点你在命令提示符窗口中设置，就只对当前命令提示符窗口窗口有效，总不能每次打开一个新的命令提示符窗口都要设置一遍吧，这样就没有意义了。<br>
要做到对所有窗口都生效,请看我的另一篇文章：[cmd启动时自动执行批处理.md](https://github.com/hosxy/Settings/blob/master/Windows/cmd/cmd%E5%90%AF%E5%8A%A8%E6%97%B6%E8%87%AA%E5%8A%A8%E6%89%A7%E8%A1%8C%E6%89%B9%E5%A4%84%E7%90%86.md)

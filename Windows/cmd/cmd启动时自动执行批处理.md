有时候我们希望 cmd 启动的时候就能执行一条或者多条命令，但是 cmd 又没有 linux 下类似 `profile` `bashrc`这种东西。 <br>

其实 cmd 也有个类似的东西，命令提示符窗口下输入 `cmd /?` 打开 cmd 帮助，向下翻，你会发现会搜索注册表的两个键值，并执行这两个键值对应的命令。这两个键值是：
```
HKEY_LOCAL_MACHINE\Software\Microsoft\Command Processor\AutoRun
HKEY_CURRENT_USER\Software\Microsoft\Command Processor\AutoRun
```
顾名思义，第一个是对所有用户生效，第二个是对当前用户生效。 <br>

不过默认情况下是没有 AutoRun 这个键值的，需要自己新建，类型为字符串。然后把要执行的命令放到一个 `.bat/.cmd` 批处理中，然后这个键的值为该 `.bat/.cmd` 批处理的路径。然后每次打开 cmd 的时候，这个批处理都会被执行。(≧∇≦)ﾉ 。

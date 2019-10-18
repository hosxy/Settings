首先请认准 **Windows10官方下载地址:** https://www.microsoft.com/zh-cn/software-download/windows10 <br>

然后具体分两种情况:
1. 但是如果你的操作系统也是 Windows，访问这个网址就会让你下载媒体创建工具(MediaCreationTool)，然后用这个工具可以直接升级Windows，或者创建启动盘，但是这个工具下载的镜像是esd格式，并不是通用的 ISO 镜像。
2. 如果的系统不是 Windows(比如 Linux/OSX/Android)，是可以直接下载 ISO 镜像的。

可以看出如果你的操作系统是 Windows 微软就不让你直接下载 ISO 镜像，非要用他们家的 MediaCreationTool。然后这就涉及怎么判断是什么操作系统，
经测试微软应该是根据浏览器UA(UserAgent)来判断操作系统的，所以改下UA就行了(我这里用了 Firefox 自带的响应设计模式，当然你也可以安装个改UA的扩展来实现)。

具体操作步骤如下：
1. 打开 [windows10官方下载地址](https://www.microsoft.com/zh-cn/software-download/windows10)
2. 打开菜单，然后依次选择 `Web开发者 -> 响应设计模式`,或者直接按 `Ctrl + Shift + M` 打开，再按一遍就可以关掉
3. 然后书签栏下面会有一行，然后设备选 `Kindle Fire HDX`，选其他也可以，只要不是搭载 Windows 的设备就行，然后刷新网页。
4. 是不是看到网页变成了 `下载 windows 10 光盘映像(ISO文件)` (吐嘈下，这翻译是不是机翻的)，之后就不用多说了吧，该怎么选就怎么选。

**Tips: 其他浏览器,比如`Chrome`,`Microsoft Edge`等也都可以做到，只是在操作上略有区别而已**

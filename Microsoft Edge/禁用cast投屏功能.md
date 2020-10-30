# Windows：使用注册表关闭cast投屏功能
1. 按下 `win+r` 组合键打开运行，输入：`regedit` 按下回车键按钮打开注册表；
2. 定位到以下注册表项(没有则创建)：`HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Edge`
3. 新建 `EnableMediaRouter`，键值类型为 `DWORD`，基数为十六进制，数值数据为 `0`

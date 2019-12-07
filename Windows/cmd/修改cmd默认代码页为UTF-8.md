# 方法一
参照另一篇文章 [cmd 启动时自动执行批处理](https://github.com/hosxy/Settings/blob/master/Windows/cmd/cmd%E5%90%AF%E5%8A%A8%E6%97%B6%E8%87%AA%E5%8A%A8%E6%89%A7%E8%A1%8C%E6%89%B9%E5%A4%84%E7%90%86.md),在批处理里面加一句 `chcp 65001`就可以了。

# 方法二
此方法通过直接修改注册表实现：
1. 按下win+r 组合键打开运行，输入：regedit 按下回车键打开注册表编辑器
2. 定位到以下键值：`HKEY_CURRENT_USER\Console\%SystemRoot%_SYSTEM32_cmd.exe`
3. 在右侧找到`CodePage`项，基数为`十六进制`，数值数据为:`fde9`(基数值也可为`十进制`，此时数据数值应为`65001`)

## 方法1：依然显示 “在此处打开powershell窗口”，但实际打开的是 cmd
1、按下win+r 组合键打开运行，输入：regedit 按下回车键按钮打开注册表；  
2、注册表左侧定位到以下注册表键值：HKCR\Directory\Background\shell\Powershell\command  
3、将右侧默认字符串值改成：cmd.exe /s /k pushd "%V" 点击确定保存接口！

## 方法2：同时显示“在此处打开命令窗口”和 “在此处打开powershell窗口”(可删除)
1、按下win+r 组合键打开运行，输入：regedit 按下回车键按钮打开注册表； <br>
2、注册表左侧定位到以下注册表键值：HKCR\Directory\Background\shell\cmd   <br>
3、将右侧 HideBasedOnVelocityId 数值数据改成：0 ，  <br>
4、新建 ShowBasedOnVelocityId 类型为 DWORD，基数为 16进制，数值数据为 639bc8  <br>
5、注册表左侧定位到以下注册表键值：HKCR\Directory\Directory\shell\cmd  <br>
6、将右侧 HideBasedOnVelocityId 数值数据改成：0 ，  <br>
7、新建 ShowBasedOnVelocityId 类型为 DWORD，基数为 16进制，数值数据为 639bc8  <br>
### 以下为隐藏 "在此处打开powershell窗口"
8、定位到以下注册表键值：HKCR\Directory\Background\shell\Powershell 和 HKCR\Directory\Directory\shell\Powershell  <br>
9、新建 HideBasedOnVelocityId 类型为 DWORD，基数为 16进制，数值数据为 639bc8   <br>

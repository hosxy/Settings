## 1、什么是本地回环
本地回环就是指`localhost`或者`127.0.0.1`，

## 2、获取 UWP 应用的 SID 或者 PackageFamilyName
### 2.1 获取uwp应用的SID
根据[微软官方文档](https://docs.microsoft.com/zh-cn/previous-versions/windows/apps/hh780593(v=win.10)) ，uwp应用的SID可以在此注册表项中找到
```
HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\Windows\CurrentVersion\AppContainer
```
但是这过于麻烦，也不好找，所以不推荐这种。<br>
### 2.2 获取uwp应用PackageFamilyName
打开PowerShell，执行以下命令
```
Get-AppxPackage | Select Name, PackageFamilyName
```
就会输出所有UWP应用的 PackageFamilyName。

## 3、开启本地回环访问权限
以管理员权限打开命令提示符，执行以下命令：
```
CheckNetIsolation.exe LoopbackExempt –a –p=<SID>
```
或者
```
CheckNetIsolation.exe LoopbackExempt -a -n=<PackageFamilyName>
```

## 4、删除本地回环访问权限
以管理员权限打开命令提示符，执行以下命令：
```
CheckNetIsolation.exe LoopbackExempt –d –p=<SID>
```
或者
```
CheckNetIsolation.exe LoopbackExempt -d -n=<PackageFamilyName>
```
使用以下命令可以删除所有应用的本地回环访问权限
```
CheckNetIsolation.exe -c
```

## 4、查看可以拥有访问本地回环代理的应用列表
```
CheckNetIsolation.exe LoopbackExempt -s
```


**注：由于SID不好找，个人建议传递PackageFamilyName参数。**


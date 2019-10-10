 对于全新安装的 Firefox ，从Firefox 69 版本起默认不再加载userChrome.css了，老版本已经使用了 userChrome.css 再升级到 69 不受影响。
 
 地址栏输入 `about:config ` <br>
 然后在搜索栏输入 `toolkit.legacy` 然后找到 `toolkit.legacyUserProfileCustomizations.stylesheets`，将其值改为 true 就可以了。

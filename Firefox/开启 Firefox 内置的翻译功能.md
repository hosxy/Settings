其实 Firefox 也有类似 chrome 那种的整页翻译功能，只不过默认没有开启。而且由于 Mozilla 本身并没有翻译相关的业务，所以这个功能是依赖第三方的翻译平台，比如 Google Translae，Microsoft Translate, Yadenx Translate等。不过由于 Google 和 Mozilla 处于竞争关系，Google的早就不能用了，微软的听说也不能用了，不过 Yandex 的还可以用。(Yandex 在俄罗斯是一家很有名的公司，和中国的 BAT 差不多)。

1. 要使用 Yandex 来提供的翻译功能，必须要有相关的 APIKey，所以必须注册一个 Yandex 帐号，怎么注册 Yandex 帐号就不多说了。
2. 注册完帐号后打开这个网页：https://translate.yandex.com/developers/keys ，生成一个 APIKey，其值是一个很长的字符串。
3. 然后在 Firefox 地址栏输入 `about:config`，然后搜索 `translation`。
    + 将`browser.translation.detectLanguage` 的值改为 `true`。
    + 将`browser.translation.engine`的值改为 `Yandex` (注意大小写)。
    + 将`browser.translation.ui.show`的值改为 `true`。
    + 将`browser.translation.yandex.apiKeyOverride`(没有就新建一个)的值改为你刚刚生成的那个APIKey的值(就是那个很长的字符串)。
4. 这时候已经可以用了，如果你细心的话你会发现在 Firefox 的设置->常规->语言下面多了一个`翻译网页内容`的选项。可以用这个来全局开关翻译功能。

因为 Yandex 的服务器不在中国，所以速度不怎么好。<br>
而且说实话这个功能做得实在是不怎么样，只要是个非中文网页地址栏会有一个翻译的小图标并且就会弹出一个是否要翻译的横幅，真是相当令人讨厌。<br>
我的做法是将经常遇到的语言比如：`English` 加入到不翻译语言列表(点下横幅里的`选项->不翻译English`)，这样就不会自动弹出是否翻译的横幅了，要翻译的时候点下地址栏翻译的小图标，那个横幅就会出现。<br>
最后放个效果图：
![](https://user-images.githubusercontent.com/17108640/67200445-59972600-f436-11e9-8e77-95d156f0107a.png)

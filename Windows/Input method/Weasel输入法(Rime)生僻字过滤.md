## 修改配置文件
首先在Weasel输入法的用户文件夹里新建/修改文件 `luna_pinyin_simp.custom.yaml`,然后写入以下内容：
``` yaml
patch:
   
  switches:
    - name: ascii_mode
      reset: 0
      states: [ 中文, 西文 ]
    - name: full_shape
      states: [ 半角, 全角 ]
    - name: zh_simp                                     # 简繁转换
      reset: 1
      states: [ 漢字, 汉字 ]
    - name: ascii_punct
      states: [ 。，, ．， ]
    - options: ["utf8", "gbk", "gb2312"]                # 字符集选单
      reset: 0                                          # 默认 UTF-8
      states:
        - UTF-8
        - GBK
        - GB2312
        
  engine/filters:
    - simplifier
    - uniquifier
    - charset_filter@gbk                                # GBK过滤
```
然后重新部署输入法。

## 设置
按 ` Ctrl+`  键打开Weasel设置，选择 `朙月拼音•简化字` 之后选择 `GBK`，然后在打字是不是发现那些生僻字已经没有了。

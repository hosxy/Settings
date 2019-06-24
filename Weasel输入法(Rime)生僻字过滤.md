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
    - options: ["gbk","utf8"]                           # 字符集选单
      reset: 0                                          # 默认 GBK
      states:
        - GBK
        - UTF-8
        
  engine/filters:
    - simplifier
    - uniquifier
    - charset_filter@gbk                                # GBK过滤
```
然后重新部署输入法。然后在打字是不是发现那些生僻字已经没有了。

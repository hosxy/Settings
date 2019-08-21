## 生僻字过滤
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

## emoji 支持
如果你同时用了 emoji 支持的话，上面的方案同时也会把 emoji 过滤掉，毕竟 emoji 不在 GBK 的范围之内。如果需要启用GBK过滤的同时，保留emoji，需要略微修改下配置文件，使用`charset_filter@gbk+emoji` 来替代`charset_filter@gbk`,顽症内容如下：
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
    - options: ["gbk+emoji","utf8"]                     # 字符集选单
      reset: 0                                          # 默认 GBK
      states:
        - GBK
        - UTF-8
        
  engine/filters:
    - simplifier
    - uniquifier
    - charset_filter@gbk+emoji                          # GBK+emoji过滤
```

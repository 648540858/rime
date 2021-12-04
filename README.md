## Rime 鼠须管（Squirrel）朙月拼音、小鹤双拼、自然码双拼配置详解

![](https://i.imgur.com/nm2Wk1F.jpg)
Rime 鼠须管对于首次上手的用户来说有点难，建议先看下目录（解剖了大部分细节）。日积月累，该输入法会越用越上手。

---

### 主要特点

* 朙月拼音、小鹤双拼、自然码双拼、大写数字
* 词库不丢失
* 包含约 170 万[搜狗词库](https://github.com/qingmail/sogou-dict-transform)（无重码）
* Emoji 与 Mac 同步
* 动态输入时间、日期、星期
* 速度快、开源、不联网保护隐私、DIY 空间大

>欢迎加入 [Telegram 电报群](https://t.me/V2EXPro) 、[Twitter](https://twitter.com/qingmail)，更新日志：[点击这里](https://github.com/qingmail/rime/wiki#%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)。

***

### 目录

1. [安装输入法](#安装输入法)
2. [备份安装包](#备份安装包)
3. [定制输入法](#定制输入法)
4. [输入方案](#输入方案)
5. [大写数字](#大写数字)
6. [候选词个数](#候选词个数)
7. [中英文切换键](#中英文切换键)
8. [快捷键](#快捷键)
9. [回车清码](#回车清码)
10. [词库文档格式](#词库文档格式)
11. [外挂词库](#外挂词库)
12. [搜狗词库转换方法](https://github.com/qingmail/sogou-dict-transform)
13. [修改 Emoji](#修改-emoji)
14. [载入外挂词库和 Emoji](#载入外挂词库和-Emoji)
15. [关闭 Emoji](#关闭-emoji)
16. [快捷符号](#快捷符号)
17. [模糊音](#模糊音)
18. [智能纠错](#智能纠错)
19. [动态时间、日期、星期](#动态时间日期星期)
20. [自定义短语](#自定义短语)
21. [皮肤](#皮肤)
22. [开启关闭中文输入和中文状态输出英文标点](#开启关闭中文输入和中文状态输出英文标点)
23. [删除错词](#删除错词)
24. [删除生僻字](https://github.com/qingmail/rime-rare-word)
25. [同步](#同步)
26. [报错日志](#报错日志)
27. [卸载](#卸载鼠须管)
---
### 安装输入法

下载[鼠须管](https://rime.im/)并安装。菜单栏点选【ㄓ】图标，开始使用输入法。

默认繁体输出，通过快捷键 `Control+｀` 切换输入方式，例如选择【朙月拼音·简化字】简体输出。

> 注：建议打开鼠须管通知，之后部署配置文件会实时提示是否成功。

* 程序配置路径: `/Library/Input Methods/Squirrel.app/Contents/SharedSupport`
* 用户配置路径: `~/Library/Rime`（一般情况下，只用到这个）

---

### 备份安装包

防止定制输入法操作不当无法恢复，建议先为初始配置做个备份。在【终端】中输入或粘贴以下命令，按回车键。

```
cp -r ~/Library/Rime ~/Library/Rime.bak
```

配置文件路径（`~/Library/Rime`）多出【Rime.bak】即备份文件。

![](https://tvax2.sinaimg.cn/large/008jMPXrgy1gr7uvc1gflj31m40v00vw.jpg)

> 还原方法：【Rime】文件夹清空，将【Rime.bak】内的文件粘贴过去，重新部署。

---

### 定制输入法

下载[配置文件](https://github.com/qingmail/rime/archive/refs/heads/master.zip)解压得到【配置文件】和【花园明朝字体】，因为 macOS 不含部分生僻字，所以将花园明朝字体安装到字体册。

点选**用户设定**（`~/Library/Rime`）打开目录文件夹，将【配置文件】 里所有文件复制粘贴进去，并选择覆盖。

![](https://ww1.sinaimg.cn/large/008eZBHKgy1gn45cxyphgj31e20ca7e9.jpg)

```
# 定制配置文件说明
custom_phrase.txt                 # 自定义短语
default.custom.yaml               # 全局设置
double_pinyin_flypy.custom.yaml   # 小鹤双拼
double_pinyin_flypy.schema.yaml   # 小鹤双拼
double_pinyin.custom.yaml         # 自然码双拼
double_pinyin.schema.yaml         # 自然码双拼
easy_en.dict.yaml                 # 英文词典
easy_en.schema.yaml               # 英文词典
luna_pinyin_simp.custom.yaml      # 朙月拼音·简化字
luna_pinyin_simp.schema.yaml      # 朙月拼音·简化字
luna_pinyin.custom.yaml           # 朙月拼音
luna_pinyin.schema.yaml           # 朙月拼音
luna_pinyin.extended.dict.yaml    # 挂载词库
luna_pinyin.dict.yaml             # 词库（汉字）
luna_pinyin.sogou.dict.yaml       # 词库（搜狗）
luna_pinyin.zonghe.dict.yaml      # 词库（综合）
numbers.schema.yaml               # 大写数字
opencc                            
  ├── emoji_word.txt              # Emoji
  └── emoji.json           
rime.lua                          # 动态时间、日期、星期
squirrel.custom.yaml              # 皮肤
```


点击**重新部署**（快捷键 `Control+Option+｀`）完成定制。如对功能进行探索调整，继续往下看。

> 注：修改任何文件都要“重新部署”方可生效；本配置里搜狗词库较大，第一次部署时间会稍长，请耐心等待。

![](https://ww1.sinaimg.cn/large/008eZBHKgy1gn45fjrwu3j31e00c87e7.jpg)


---
### 输入方案

如果输入方案配置文件（例如下面的大写数字）已加入配置文件内，需要将输入方案名称添加进 `default.custom.yaml`（按 `Control+｀` 切换输入方案）。

```
patch:
  schema_list:
    - schema: luna_pinyin_simp      # 朙月拼音简化字
    - schema: luna_pinyin           # 朙月拼音
    - schema: double_pinyin_flypy   # 小鹤双拼
    #- schema: double_pinyin         # 自然码双拼
    - schema: numbers               # 大写数字
```

> 其他输入方案[点击这里](https://github.com/rime/plum)。推荐使用 [Visual Studio Code](https://code.visualstudio.com/) 打开 `.yaml` 文件（[Tab](https://twitter.com/qingmail/status/1357338760623529988) 键可能需要修改，因人而异）。

---

### 大写数字

大写数字输入方案配置文件 `numbers.schema.yaml`。将下面代码添加在 `default.custom.yaml`（默认已添加）。

```
- schema: numbers               # 大写数字
```
用法：
| 按键  |  输出 |✂️|按键（按住Shift）|输出 |
|---|---|---|---|---|
| 1234567890  | 壹贰叁肆伍陆柒捌玖零  |✂️| 1234567890  | 一二三四五六七八九〇  |
| wqbsjfd.  |  万仟佰拾角分第点 |✂️|  wqbsjfd. |  万千百十角分第点 |
|  z | 整之  |✂️| z  | 整之  |
|  y | 元月亿  |✂️| y  | 元月亿  |


![](https://i.loli.net/2021/04/14/qYxrowydRaAUvzP.gif)

---

### 候选词个数

打开 `default.custom.yaml` 文件，数字即候选词个数。

```
  menu/page_size: 9   # 候选词个数
```

---

### 中英文切换键

打开 `default.custom.yaml` 文件，设置切换中英文。

```
  ascii_composer/good_old_caps_lock: true   # 若为true，caps只切换大小写
  ascii_composer/switch_key:
    Caps_Lock: commit_code                    
    Shift_L: commit_code   # 左Shift，关闭noop
    Shift_R: noop          # 右Shift
    Control_L: noop        # 左Control
    Control_R: noop        # 右Control
```

> 注1：Mac 上鼠须管不能区分左右 `Shift` ，因此左右 `Shift` 键作用一样。
>
> 注2：如果 `caps` 键不能切换大小写，打开 Mac 系统偏好设置 - 键盘 - 输入法 - 取消勾选“使用大写锁定键切换“美国”输入模式”。

---

### 快捷键

打开 `default.custom.yaml` 文件，设置翻页和其他快捷键（关闭某项在前面添加 `#`）。

```
key_binder/bindings: # 翻页
  - { when: composing, accept: ISO_Left_Tab, send: Page_Up }  # "tab"翻页
  - { when: composing, accept: Shift+Tab, send: Page_Up }
  - { when: composing, accept: Tab, send: Page_Down }     
  - { when: paging, accept: minus, send: Page_Up }            # "-"上一页
  - { when: has_menu, accept: equal, send: Page_Down }        # "="下一页
  - { when: paging, accept: bracketleft, send: Page_Up }      # "["上一页
  - { when: has_menu, accept: bracketright, send: Page_Down } # "]"下一页
  #- { when: paging, accept: comma, send: Page_Up }            # ","上一页
  #- { when: has_menu, accept: period, send: Page_Down }       # "."下一页

  #- {accept: "Control+a", send: Home, when: composing}                   # 光标移至首
  #- {accept: "Control+e", send: End, when: composing}                    # 光标移至尾
  #- {accept: "Control+Shift+1", select: .next, when: always}             # 切换输入方案
  #- {accept: "Control+Shift+2", toggle: ascii_mode, when: always}        # 中英文切换
  #- {accept: "Control+Shift+3", toggle: full_shape, when: always}        # 全角/半角切换
  - {accept: "Control+Shift+4", toggle: simplification, when: always}    # 繁简体切换
  #- {accept: "Control+Shift+5", toggle: extended_charset, when: always}  # 通用/增广切换（显示生僻字）
```

更多快捷键：[点击这里](https://github.com/rime/rime-prelude/blob/master/key_bindings.yaml)

---

### 回车清码

打开 `default.custom.yaml` 文件，找到下面代码（默认关闭，若开启去掉 `#`）。

```
  #- {accept: Return, send: Escape, when: composing} 
```

---

### 词库文档格式

新建文件，命名格式为 <词库名>.dict.yaml，其他要求见下图。

例如朙月拼音词库，则为 `luna_pinyin.词库名.dict.yaml`。

![](https://i.imgur.com/zcDOdod.png)

---

### 外挂词库

打开 `luna_pinyin.extended.dict.yaml` 文件，找到 `import_tables`，将词库名称添加进去。

![](https://i.imgur.com/fxOh26P.png)

---

### 修改 Emoji

打开 opencc 文件夹内 `emoji_word.txt` 修改 Emoji。

规则：`字符 + 字符 + Emoji`；字符之间用 **tab 键**分隔，字符和 Emoji 之间用**空格键**分隔。

![](https://tva2.sinaimg.cn/large/008eZBHKly1goxgt4aawqj31ao0geq4o.jpg)

---

### 载入外挂词库和 Emoji

打开 `luna_pinyin_simp.custom.yaml` 文件，载入中 / 英文词库和 Emoji。

```
  engine/filters:
      - simplifier
      - simplifier@emoji_conversion
      - uniquifier
      - charset_filter@gbk              # (※3) GBK 过滤
      - single_char_filter

  emoji_conversion:
    opencc_config: emoji.json
    option_name: show_emoji
    tags: abc
    # tips: all    # Emoji 显示注释（去掉 # 开启）

# 改写拼写运算，含英文的词汇（luna_pinyin.cn_en.dict.yaml）不影响简拼
  "speller/algebra/@before 0": xform/^([b-df-hj-np-tv-z])$/$1_/

#  载入朙月拼音扩充词库
  "translator/dictionary": luna_pinyin.extended

# 加载easy_en依赖
  "schema/dependencies/@1": easy_en
# 载入翻译英文的码表翻译器，取名为 english
  "engine/translators/@4": table_translator@english
# english翻译器的设定项
  english:
    dictionary: easy_en
    spelling_hints: 9
    enable_completion: false      # 是否启用英文输入联想补全
    enable_sentence: false
    initial_quality: 1            # 调整英文候选词的位置
```
---

### 关闭 Emoji

按 `Control + ｀` 组合键，选择输入方案。

* 关闭 Emoji 选择 🈶 → 🈚️
* 开启 Emoji 选择 🈚️ → 🈶

![](https://tvax4.sinaimg.cn/large/008eZBHKly1gp3nfu2fenj31ao04s3z0.jpg)

---

### 快捷符号

打开 `luna_pinyin_simp.custom.yaml` 文件，找到 `punctuator` 修改快捷 Emoji 和符号。

效果：

![](https://i.imgur.com/Ca784F1.png)

```
 # 符号快速输入和部分符号的快速上屏
  punctuator:
    import_preset: symbols
    symbols:
      "/fs": [½, ‰, ¼, ⅓, ⅔, ¾, ⅒ ]
      "/xh": [ ＊, ×, ✱, ★, ☆, ✩, ✧, ❋, ❊, ❉, ❈, ❅, ✿, ✲]
      "/dq": [🌍,🌎,🌏,🌐,🌑,🌒,🌓,🌔,🌕,🌖,🌗,🌘]
      "/sg": [🍇,🍉,🍌,🍍,🍎,🍏,🍑,🍒,🍓,🍗,🍦,🎂,🍺,🍻]
      "/dw": [🙈,🐵,🐈,🐷,🐨,🐼,🐾,🐔,🐬,🐠,🦋]
      "/bq": [😀,😁,😂,😃,😄,😅,😆,😉,😊,😋,😎,😍,😘,😗]
      "/ss": [💪,👈,👉,👆,👇,✋,👌,👍,👎,✊,👊,👋,👏,👐]
    half_shape:
      "#": "#"
      "*": "*"
      "`": "`"
      "~": "~"
      "@": "@"
      "=": "="
      '\': "、"
      "%": "%"
      "$": ["¥", "$", "€", "£", "¢", "¤"]
      "|": ["|", "｜", "·", "・", "§", "¦", "‖", "︴"]
      "/": ["/", "÷"]
      "'": { pair: ["「", "」"] }
      "[": ["【", "〔", "［"]
      "]": ["】", "〕", "］"]
      "<": "《"
      ">": "》"

  recognizer/patterns/punct: "^/([a-z]+|[0-9]0?)$"
```



---

### 模糊音

示例：打开朙月拼音简化字 `luna_pinyin_simp.custom.yaml ` 文件，找到下面代码进行设置，开启去掉前面 `#`。 

```
# 模糊拼音
  'speller/algebra':
    - erase/^xx$/                      # 第一行保留

    # 模糊音定義
    # 需要哪組就刪去行首的 # 號，單雙向任選
    #- derive/^([zcs])h/$1/             # zh, ch, sh => z, c, s
    #- derive/^([zcs])([^h])/$1h$2/     # z, c, s => zh, ch, sh

    #- derive/^n/l/                     # n => l
    #- derive/^l/n/                     # l => n
```

---

### 智能纠错

示例：打开朙月拼音简化字 `luna_pinyin_simp.custom.yaml` 文件，找到下面代码进行设置，关闭前面添加 `#`。

```
    # 自動糾正一些常見的按鍵錯誤
    - derive/([aeiou])ng$/$1gn/        # dagn => dang 
    - derive/([dtngkhrzcs])o(u|ng)$/$1o/  # zho => zhong|zhou
    - derive/ong$/on/                  # zhonguo => zhong guo
    - derive/ao$/oa/                   # hoa => hao
    - derive/([iu])a(o|ng?)$/a$1$2/    # tain => tian
```

---

### 动态时间、日期、星期
打开 `Rime.lua` 文件修改编码和格式。默认日期= `date`，可以修改为自己喜欢的简短编码。

* `rq` = `日期`
* `sj` = `时间`
* `xq` = `星期`

![](https://i.imgur.com/bB820q5.png)

再将下面代码添加在对应的输入方案里，例如：朙月拼音·简化字方案即添加在 `luna_pinyin_simp.custom.yaml`。

```
# librime-lua 输入动态时间和日期
  "engine/translators/@6": lua_translator@date_translator
```

---

### 自定义短语

打开 `custom_phrase.txt` 文件编辑短语。规则：`文字 + 编码 + 权重`，使用 Tab 键分隔。

示例：

```
Rime	rime	4
鼠须管	rime	3
https://rime.im/	rime	2
Squirrel	rime	1
```


![](https://i.loli.net/2021/02/23/S3z1lxFm8Kws6nW.png)

> 注：自定义短语始终显示在第一候选项，无法单独设置为其他后选项。

---
### 皮肤

打开 `squirrel.custom.yaml` 文件，将皮肤代码添加进去。在 `style/color_scheme:` 后面修改名称即可更换皮肤。

![](https://i.imgur.com/Jmf49zP.png)

更多皮肤效果：[点击这里](https://github.com/qingmail/rime-pifu)。

* 每 8bit 一组，从低位到高位分别代表 Red、Green、Blue、Alpha，共 32bit。
* Alpha 值（如果界面支持）是可选的，默认为 `0xF` F 即不透明。
* 把颜色值写为十六进制数，即 `0xAABBGGRR` 或 `0xBBGGRR`。

![](https://ww1.sinaimg.cn/large/008eZBHKgy1gn45ifbfhnj311r0kw769.jpg)

---

### 开启关闭中文输入和中文状态输出英文标点

打开 `squirrel.custom.yaml` 文件，找到 `app_options:`，添加软件名和是否允许代码。

* `ascii_mode: ture` 关闭中文输入
* `ascii_mode: false` 开启中文输入
* `ascii_punct: true` 开启中文输入时输出英文标点

示例：下图粉框内表示 Visual Studio Code 支持中文输入，但标点是英文。

![](https://i.imgur.com/waa5gAJ.png)

> **延伸：如何获取程序名称？**
> 1. 打开**活动监视器**，选中对应程序，上方 `···` 里点击**取样进程**。
> 2. 找到 `Identifier`，后面显示即为该程序名称。
> ![](https://i.imgur.com/W8hUnK1.png)


---

### 删除错词

将光标（`↑` `↓`或`←` `→`）移到要删除的词组上，按 `Shift + Fn + Delete` 键（第三方键盘按   `Control + Delete`）。

> 注：只能从用户词典中删除词组；词库里词组只会取消其调频顺序。

---

### 同步

#### 词库同步到 iCloud

1. 在 iCloud 云盘内新建个文件夹，例如 `Rime`。
2. 打开配置文件 ` installation.yaml`，修改 `installation_id` ID，例如 `mac`。
3. 再添加路径代码（admin 为 Mac 用户名）。

```
 sync_dir: "/Users/admin/Library/Mobile Documents/com~apple~CloudDocs/Rime"
```

示例：下图路径意思是同步至 iCloud 下 Rime 文件夹内。

![I](https://i.imgur.com/Q4g5Out.png)


4. 点选菜单栏【ㄓ】-【同步用户数据】，打开 iCloud 云盘查看同步成功。

![](https://i.imgur.com/bLhzWYm.png)

#### iCloud 同步至新电脑
1. 将之前网盘里的备份词库文件拷贝至电脑 iCloud 云盘（如果 iCloud 是同一个 Apple ID 则无需拷贝）。
2. 打开已经配置好的鼠须管配置文件 ` installation.yaml`，将 **ID** 和 **路径** 修改成和备份词库文件一至，重新部署完成词库同步。

更多同步方案：[点击这里](https://github.com/rime/home/wiki/UserGuide#%E5%90%8C%E6%AD%A5%E7%94%A8%E6%88%B6%E8%B3%87%E6%96%99)

---

### 报错日志

打开**终端**输入 `$TMPDIR/rime.Squirrel.INFO` 按回车键，复制路径地址在访达中打开。

![](https://tva3.sinaimg.cn/large/008eZBHKgy1gq3krzyftbj311w09qgm4.jpg)

找到【rime.squirrel.INFO】文件，右击点选**显示原身**得到日志文件。

![](https://tvax2.sinaimg.cn/large/008eZBHKgy1gq3kwsm5vvj31l00outbn.jpg)

---

### 卸载鼠须管

1. 打开系统盘好设置 - 键盘 - 输入法，移除【鼠须管】。
2. 打开访达并按下 `command + shift + G` 前往 `/Library/Input Methods` 文件夹，删除【Squirrel.app】。
3. 如上，前往 `~/Library` 并删除文件夹【Rime】。
4. 重新登入系统，确保清理完毕。

🔝[返回目录](#目录)


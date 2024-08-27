# 写在前面
学习正则表达式的过程中总是被其复杂的语法和内容所困扰，虽然通过简单的学习正则表达式还算是一个简单易用的工具。
**但是** 一个很烦人的问题是 **这些复杂的语法**实属等于`一学就会，一用就忘`

```所以想到将正则表达式的内容整理成一个自己的文档，方便之后的翻阅和查找🔍```

```话不多说，我们开始吧```✊️

`别着急，慢慢学，才比较快` 💪

`如果你想一口气学完，那也没有问题，甚至是极好的，但`**千万**`别忘了即时的复习和常回来看看` ⛽️

🤪 我有个很喜欢的诗歌，这里也分享给你 👋 `追风赶月莫停留，平芜尽处是春山` 👋

## 内容

#### 介绍
`Regular expression`

> 正则表达式是一种用于模式匹配和搜索文本的工具。
>
> 正则表达式是一种强大的文本处理工具，用于描述、匹配一系列符合特定模式的字符串。
>
> 正则表达式可以应用于各种编程语言和文本处理工具中，如 JavaScript、Python、Java、Perl 等。
>
> 在编写处理字符串的程序或网页时，经常会有查找符合某些复杂规则的字符串的需要。正则表达式就是用于描述这些规则的工具。换句话说，正则表达式就是记录文本规则的代码
>
> 正则表达式是一组由字母和符号组成的特殊文本, 它可以用来从文本中找出满足你想要的格式的句子。
>

#### 正则表达式的核心概念

> `普通字符`：如a到z之间的字母
>
> `特殊字符(元字符)`：具有特殊含义的字符，用于定义匹配规则
>
#### 正则表达式的主要用途

> `匹配` ：从文本中查找符合特定模式的字符串
>
> `查找`：在文本中搜索特定模式的字符串
>
> `替换` ：将符合特定模式的字符串替换为其他字符串
>
#### 正则表达式的应用场景

> `数据提取` :从日志文件、数据库记录等中提取特定信息
>
> `表单验证` : 在网页表单中验证用户输入的数据是否符合特定格式，如邮箱地址、密码强度等
>
> `文本处理` :  在大量文本中查找、替换或提取符合特定模式的文本片段
>

#### 正则表达式的工具推荐

> https://tool.chinaz.com/tools/regexgenerate/
>
> https://regexr.com/ **推荐指数** ⭐️⭐️⭐️⭐️⭐️
>
> https://regexper.com/
>
> https://regexper.com/
>
> https://imageslr.github.io/regexone-cn/lesson/introduction_and_abcs.html
>
> https://www.jyshare.com/front-end/9064/
>
> https://regex101.com/
>
> https://deerchao.cn/tools/regex_tester/index.htm
>
> https://codejiaonang.com/#/course/regex_chapter1
>
> https://regex.ai/?utm_source=appinn.com
>
> https://www.regexpal.com/
### 元字符 

|代码|解释|
|:----:|----|
|.|```匹配除换行符以外的任意字符```|
|[ ]|```字符类，匹配方括号中包含的任意字符```|
|[^ ]|```否定字符类。匹配方括号中不包含的任意字符```|
|*|```匹配前面的子表达式零次或多次```|
|+|```匹配前面的子表达式一次或多次```|
|?|```匹配前面的子表达式零次或一次```|
|`\|`|	```或运算符，匹配符号前或后的字符```|
|`\`|```转义字符,用于匹配一些保留的字符 `[ ] ( ) { } . * + ? ^ $```|
|{n}|```匹配确定的 n 次```|
|{n,m}|```花括号，匹配前面字符至少 n 次，但是不超过 m 次```|
|{n,}|```至少匹配n 次```|
|(xyz)|```字符集，匹配与 xyz 完全相等的字符串```|
|^|```匹配行的开始```|
|$|```匹配行的结束```|

### 转义符

转义符的作用是保留正则表达式中一些特殊的元字符

例子：

|正则表达式|结果|
|:-----:|:----:|
|java`\.`juc|java.juc|
|python`\.`numpy|python.numpy|
|c++`\.`gc|c++.gc|
|c`:\\`usr|c:usr|

### 正则表达式的具体使用

`[ABCDE]` `匹配[]中的所有元素` `主要有[]中的任意一个元素都算匹配到了`

`[^ABCDE]` `匹配除了 [...] 中字符的所有字符` `就是匹配F-Z之间的字符`

`[A-Z]` `[A-Z] 表示一个区间，匹配所有大写字母` 

`[a-z]` `[a-z] 表示一个区间，匹配所有的小写字母`

`[^a-z]` `反向范围字符。匹配不在指定的范围内的任何字符`

`[\w]` `匹配字母、数字、下划线，等价于 [A-Za-z0-9_]`

`[\d]` `匹配任意一个阿拉伯数字（0 到 9）。等价于 [0-9]`

`[.]` `匹配除换行符之外的任何单个字符` `[...a]匹配3个(几个点就几位)任意字符后面跟着是a的内容`

`[*]` `匹配`**前面**`的模式零次或多次`

`[+]` `匹配`**前面**`的模式至少一次或多次` 

`[?]` `匹配`**前面**`的模式零次或一次`

`[{n}]` `匹配`**前面**`的模式恰好 n 次`

`[{n,}]` `至少匹配 n 次`

`[{n,m}]` `匹配至少 n 次，至多 m 次`

`(pattern)` `匹配 pattern 并捕获该匹配的子表达式`

`(?:pattern)` `匹配 pattern 但不捕获该匹配的子表达式，即它是一个非捕获匹配，不存储供以后使用的匹配`

`(?=pattern)` `执行正向预测先行搜索的子表达式，该表达式匹配处于匹配 pattern 的字符串的起始点的字符串。`

`(?!pattern)` `执行反向预测先行搜索的子表达式，该表达式匹配不处于匹配 pattern 的字符串的起始点的搜索字符串。`

`x|y` `匹配 x 或 y`

`\b` `匹配一个字边界，即字与空格间的位置`

`\B` `非字边界匹配`

`\D` `非数字字符匹配`

`\f` `换页符匹配`

`\n` `换行符匹配`

`\r` `匹配一个回车符`

`\s` `匹配任何空白字符，包括空格、制表符、换页符等`

`\S` `匹配任何非空白字符`

`\t ` `制表符匹配`

`\v` `垂直制表符匹配`

`\xn` `匹配 n，此处的 n 是一个十六进制转义码`



#### 常用的正则表达式的示例

> `数字` `^[0-9]*$`
>
> `n位数字` `^\d{n}$`
>
> `至少n位数字` `^\d{n,}$`
>
> `m~n位数字` `^\d{m,n}$`
>
> `m~n位数字` `^\d{m,n}$`
>
> `整数` `^(-?[1-9]\d*)$`
>
> `正整数` `^[1-9]\d*$`
>
> `负整数` `^-[1-9]\d*$`
>
> `非负整数` `^(([1-9]\d*)|0)$`
>
> `非正整数` `^((-[1-9]\d*)|0)$`
>
> `浮点数` `^-?(?:[1-9]\d*\.\d*|0\.\d*[1-9]\d*|0\.0+|0)$ `
>
> `正浮点数` `^(?:[1-9]\d*\.\d*|0\.\d*[1-9]\d*)$`
>
> `浮点数` `^-(?:[1-9]\d*\.\d*|0\.\d*[1-9]\d*)$`
>
> `非正浮点数` `^(?:-(?:[1-9]\d*\.\d+|0\.\d*[1-9]\d*)|0\.0+|0)$`
>
> `非负浮点数` `^(?:[1-9]\d*\.\d+|0\.\d+|0\.0+|0)$`
>
> `一位小数` `^-?(?:0|[1-9][0-9]*)\.[0-9]{1}$`
>
> `至少一位小数` `^-?(?:0|[1-9][0-9]*)\.[0-9]{1,}$`
>
> `最多两位小数` `^-?(?:0|[1-9][0-9]*)\.[0-9]{1,2}$`
>
> `连续重复的数字` `^(\d)\1+$`
>
> `中文` `^[\u4E00-\u9FA5]+$`
>
> `全角字符` `^[\uFF00-\uFFFF]+$`
>
> `半角字符` `^[\u0000-\u00FF]+$`
>
> `大写英文字符串` `^[A-Z]+$`
>
> ` 小写英文字符串` `^[a-z]+$`
>
> `英文字符串` ` ^[A-Za-z]+$`
>
> ` 中文和数字` `^(?:[\u4E00-\u9FA5]{0,}|\d)+$`
>
> `英文和数字` `^[A-Za-z0-9]+$`
>
> `数字，英文，下划线组成的字符串` `^\w+$`
>
> `连续重复的字符串` `^(.)\1+$ `
>
> `不含字母的字符串` `^[^A-Za-z]*$`
>
> ` 长度为n的字符串` `^.{n}$`
>
> `日期(例如：2022-06-
12)` `^\d{1,4}-(?:1[0-2]|0?[1-9])-(?:0?[1-9]|[1-
2]\d|30|31)$`
>
> `日期(平闰年)` `^(?:(?!0000)[0-9]{4}-(?:(?:0[1-9]|1[0-2])-
(?:0[1-9]|1[0-9]|2[0-8])|(?:0[13-9]|1[0-2])-
(?:29|30)|(?:0[13578]|1[02])-31)|(?:[0-9]{2}
(?:0[48]|[2468][048]|[13579][26])|(?:0[48]|
[2468][048]|[13579][26])00)-02-29)$`
>
> `时间(12小时制)` `^(?:1[0-2]|0?[1-9]):[0-5]\d:[0-5]\d$`
>
> `时间(24小时制)` `^(?:[01]\d|2[0-3]):[0-5]\d:[0-5]\d$`
>
> `日期加时间(例如：2000-
11-11
23:20:21)` `^(\d{1,4}-(?:1[0-2]|0?[1-9])-(?:0?[1-9]|[1-
2]\d|30|31)) ((?:[01]\d|2[0-3]):[0-5]\d:[0-
5]\d)$`
>
> `中文名` `^[\u4E00-\u9FA5·]{2,16}$`
>
> `英文名` `^[a-zA-Z][a-zA-Z\s]{0,20}[a-zA-Z]$`
>
> `车牌号(不包括新能源)` `^[京津沪渝冀豫云辽⿊湘皖鲁新苏浙赣鄂桂⽢晋蒙陕吉闽贵
粤⻘藏川宁琼使领][A-HJ-NP-Z][A-HJ-NP-Z0-9]{4}
[A-HJ-NP-Z0-9挂学警港澳]$`
>
> `车牌号(包括新能源)` `^[京津沪渝冀豫云辽⿊湘皖鲁新苏浙赣鄂桂⽢晋蒙陕吉闽贵
粤⻘藏川宁琼使领][A-HJ-NP-Z](?:(?:[A-HJ-NP-Z0-
9]{4}[A-HJ-NP-Z0-9挂学警港澳])|(?:(?:\d{5}[AHJK])|(?:[A-HJK][A-HJ-NP-Z0-9][0-9]{4})))$`
>
> `火车车次(例如：G1234)` `^[GCDZTSPKXLY1-9]\d{1,4}$`
>
> `手机号1` `^(?:(?:\+|00)86)?1[3-9]\d{9}$`
>
> `手机号2` `^(?:(?:\+|00)86)?1(?:(?:3[\d])|(?:4[5-79])|
(?:5[0-35-9])|(?:6[5-7])|(?:7[0-8])|
(?:8[\d])|(?:9[189]))\d{8}$`
>
> `固定电话` `^(?:(?:\d{3}-)?\d{8}|^(?:\d{4}-)?\d{7,8})
(?:-\d+)?$`
>
> `邮编(例如：211100)` `^(?:0[1-7]|1[0-356]|2[0-7]|3[0-6]|4[0-
7]|5[1-7]|6[1-7]|7[0-5]|8[013-6])\d{4}$`
>
> `身份证` `^[1-9]\d{5}(?:18|19|20)\d{2}(?:0[1-
9]|10|11|12)(?:0[1-9]|[1-2]\d|30|31)\d{3}[0-
9Xx]$`
>
> `QQ` `^[1-9][0-9]{4,}$`
>
> `Wechat` `^[a-zA-Z][-_a-zA-Z0-9]{5,19}$`
>
> `域名` `^[a-zA-Z0-9][-a-zA-Z0-9]{0,62}(?:\.[a-zA-Z0-9][-a-zA-Z0-9]
{0,62})+$`
>
> `网址` `^(?:https?:\/\/)?[a-zA-Z0-9][-a-zA-Z0-9]{0,62}(?:\.[a-zAZ0-9][-a-zA-Z0-9]{0,62})+$`
>
> `带端口的网址 ` `^(?:https?:\/\/)?[\w-]+(?:\.[\w-]+)+:\d{1,5}\/?$`
>
> `URL` `^https?:\/\/(?:www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[azA-Z0-9()]{1,6}\b(?:[-a-zA-Z0-9()!@:%_\+.~#?&\/\/=]*)$`
>
> `Email` `^[A-Za-z0-9\u4e00-\u9fa5]+@[a-zA-Z0-9][-a-zA-Z0-9]{0,62}
(?:\.[a-zA-Z0-9][-a-zA-Z0-9]{0,62})+$`
>
> `用户名` `^[a-zA-Z0-9_-]{4,20}$`
>
> `弱密码` `^[\w]{6,16}$`
>
> `强密码` `^.*(?=.{6,})(?=.*\d)(?=.*[A-Z])(?=.*[a-z])(?=.*
[!@\.#$%^&*? ]).*$`
>
> `端口号` `^(?:[0-9]|[1-9][0-9]{1,3}|[1-5][0-9]{4}|6[0-4][0-9]
{3}|65[0-4][0-9]{2}|655[0-2][0-9]|6553[0-5])$`|
|IPv4|`^(?:(?:\d|[1-9]\d|1\d\d|2[0-4]\d|25[0-5])\.){3}(?:\d|[1-
9]\d|1\d\d|2[0-4]\d|25[0-5])$`
>
> `IPv4+端口` `^(?:(?:\d|[1-9]\d|1\d\d|2[0-4]\d|25[0-5])\.){3}(?:\d|[1-
9]\d|1\d\d|2[0-4]\d|25[0-5])(?::(?:[0-9]|[1-9][0-9]{1,3}|
[1-5][0-9]{4}|6[0-4][0-9]{3}|65[0-4][0-9]{2}|655[0-2][0-
9]|6553[0-5]))?$`
>
> `IpV6` `^(([0-9a-fA-F]{1,4}:){7,7}[0-9a-fA-F]{1,4}|([0-9a-fA-F]
{1,4}:){1,7}:|([0-9a-fA-F]{1,4}:){1,6}:[0-9a-fA-F]{1,4}|
([0-9a-fA-F]{1,4}:){1,5}(:[0-9a-fA-F]{1,4}){1,2}|([0-9afA-F]{1,4}:){1,4}(:[0-9a-fA-F]{1,4}){1,3}|([0-9a-fA-F]
{1,4}:){1,3}(:[0-9a-fA-F]{1,4}){1,4}|([0-9a-fA-F]{1,4}:)
{1,2}(:[0-9a-fA-F]{1,4}){1,5}|[0-9a-fA-F]{1,4}:((:[0-9afA-F]{1,4}){1,6})|:((:[0-9a-fA-F]{1,4}){1,7}|:)|fe80:(:[0-
9a-fA-F]{0,4}){0,4}%[0-9a-zA-Z]{1,}|::(ffff(:0{1,4})
{0,1}:){0,1}((25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9])\.)
{3,3}(25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9])|([0-9a-fA-F]
{1,4}:){1,4}:((25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9])\.)
{3,3}(25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9]))$`
>
> `ipv6+端口` `^\[(([0-9a-fA-F]{1,4}:){7,7}[0-9a-fA-F]{1,4}|([0-9a-fA-F]
{1,4}:){1,7}:|([0-9a-fA-F]{1,4}:){1,6}:[0-9a-fA-F]{1,4}|
([0-9a-fA-F]{1,4}:){1,5}(:[0-9a-fA-F]{1,4}){1,2}|([0-9afA-F]{1,4}:){1,4}(:[0-9a-fA-F]{1,4}){1,3}|([0-9a-fA-F]
{1,4}:){1,3}(:[0-9a-fA-F]{1,4}){1,4}|([0-9a-fA-F]{1,4}:)
{1,2}(:[0-9a-fA-F]{1,4}){1,5}|[0-9a-fA-F]{1,4}:((:[0-9afA-F]{1,4}){1,6})|:((:[0-9a-fA-F]{1,4}){1,7}|:)|fe80:(:[0-
9a-fA-F]{0,4}){0,4}%[0-9a-zA-Z]{1,}|::(ffff(:0{1,4})
{0,1}:){0,1}((25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9])\.)
{3,3}(25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9])|([0-9a-fA-F]
{1,4}:){1,4}:((25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9])\.)
{3,3}(25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9]))\](?::(?:[0-
9]|[1-9][0-9]{1,3}|[1-5][0-9]{4}|6[0-4][0-9]{3}|65[0-4][0-
9]{2}|655[0-2][0-9]|6553[0-5]))?$`
>
> `子网掩码` `^(?:254|252|248|240|224|192|128)\.0\.0\.0|255\.
(?:254|252|248|240|224|192|128|0)\.0\.0|255\.255\.
(?:254|252|248|240|224|192|128|0)\.0|255\.255\.255\.
(?:255|254|252|248|240|224|192|128|0)$`
>
> `MAC地址` `^(?:(?:[a-f0-9A-F]{2}:){5}|(?:[a-f0-9A-F]{2}-){5})[a-f0-
9A-F]{2}$`
>
> `图片后缀` `\.(gif|png|jpg|jpeg|webp|svg|psd|bmp|tif)+`
>
> `视频后缀` `\.(swf|avi|flv|mpg|rm|mov|wav|asf|3gp|mkv|rmvb|mp4)+`
>
> `图片链接` `(?:https?:\/\/)?[a-zA-Z0-9][-a-zA-Z0-9]{0,62}(?:\.[a-zAZ0-9][-a-zA-Z0-9]{0,62})+.+\.
(gif|png|jpg|jpeg|webp|svg|psd|bmp|tif)`
>
> `视频链接` `(?:https?:\/\/)?[a-zA-Z0-9][-a-zA-Z0-9]{0,62}(?:\.[a-zAZ0-9][-a-zA-Z0-9]{0,62})+.+\.
(swf|avi|flv|mpg|rm|mov|wav|asf|3gp|mkv|rmvb|mp4)`
>
> `WINODWS路径` `^[a-zA-Z]:(?:\\[\w\u4E00-\u9FA5\s]+)+[.\w\u4E00-\u9FA5\s]+$ `
>
> `windows的文件路径` `^[a-zA-Z]:(?:\\[\w\u4E00-\u9FA5\s]+)+$`
>
> `linux文件路径` `^\/(?:[^/]+\/)*[^/]+$`
>
> `linux文件夹路径|` `^\/(?:[^/]+\/)*$`
>
> `linux"隐藏文件"路径` `/^\/(?:[^/]+\/)*\.[^/]*/`
> 
> `MD5` `^(?:[a-f\d]{32}|[A-F\d]{32})$`
>
> `BASE64` `^\s*data:(?:[a-z]+\/[a-z0-9-+.]+(?:;[a-z-]+=[a-z0-9-]+)?)?
(?:;base64)?,([a-z0-9!$&',()*+;=\-._~:@/?%\s]*?)\s*$`
>
> `UUID` `^[a-f\d]{4}(?:[a-f\d]{4}-){4}[a-f\d]{12}$`
>
> `16进制` `^[A-Fa-f0-9]+$`
>
> `16进制颜色` `^#?([0-9a-fA-F]{3}|[0-9a-fA-F]{6})$`
>
> `SQL语句` `^(?:select|drop|delete|create|update|insert).*$`
>
> `JAVA包名字` `^(?:[a-zA-Z_]\w*)+(?:[.][a-zA-Z_]\w*)+$`
>
> `文件拓展名` `\.(?:doc|pdf|txt)`
>
> `HTML标签` `<(\w+)[^>]*>(.*?<\/\1>)?`
>
> ` HTML注释` `<!--(.*?)-->`
>
> `邮箱(只允许英文字母、数字、下划线、英文句号、以及中划线组成)，例子：gaozihang-001@gmail.com` `^[a-zA-Z0-9_-]+@[a-zA-Z0-9_-]+(\.[a-zA-Z0-9_-]+)+$`
>
> `邮箱，例子：高子航001Abc@bowbee.com.cn` `^[A-Za-z0-9\u4e00-\u9fa5]+@[a-zA-Z0-9_-]+(\.[a-zA-Z0-9_-]+)+$`
>
> `电话` `^1(3|4|5|6|7|8|9)\d{9}$`
>
> `长度为3-20的所有字符` `^.{3,20}$`
>
> `禁止输入含有%&',;=?$"等字符` `[^%&',;=?$\x22]+`
>
> `禁止输入含有~的字符` `[^~\x22]+`
>
> `零和非零开头的数字` `^(0|[1-9][0-9])$`
>
> `非零开头的最多带两位小数的数字` `^([1-9][0-9])+(.[0-9]{1,2})?$`
>
> `xml文件` `^([a-zA-Z]+-?)+[a-zA-Z0-9]+\.[x|X][m|M][l|L]$`
>
> `首尾空白字符的正则表达式` `^\s|\s*$或(^\s*)|(\s*$)`
>
> `空白行的正则表达式` `\n\s*\r`
>
> `匹配空行` `/^\s*$/`
>
> `户口簿` `/(^\d{15}$)|(^\d{18}$)|(^\d{17}(\d|X|x)$)/
>
> ` ASCII码表中的全部的特殊字符` `/[\x21-\x2F\x3A-\x40\x5B-\x60\x7B-\x7E]+/`
>
> `股票(A股)` `/^(s[hz]|S[HZ])(000[\d]{3}|002[\d]{3}|300[\d]{3}|600[\d]{3}|60[\d]{4})$/`
>
> `匹配刚好6个字符的单词` `\b\w{6}\b`
>
> `数字的千位分隔符表示法 ` `/^([01][0-9]|[2][0-3]):[0-5][0-9]$/`
>
> `匹配html的id` `/id="[^"]*"/`
>
> `大写 小写 数字 字符 任意三种和三种以上组合` `^(?![a-zA-Z]+$)(?![A-Z0-9]+$)(?![A-Z\W !@#$%^&~()-+=]+$)(?![a-z0-9]+$)(?![a-z\W_!@#$%^&*~()-+=]+$)(?![0-9\W_!@#$%^&~()-+=]+$)[a-zA-Z0-9\W_!@#$%^&*~()-+=]{3,30}$`
>
> `input 输入框不能为空字符` `/^[\s\S]*.*[^\s][\s\S]*$/`
>
> `验证文件拓展名` `^.*?\.(html|css|jpg)$`
>
> `SQL语句` ` ^(select|drop|delete|create|update|insert).*$ `
>
> `迅雷链接` `^thunderx?:\/\/[a-zA-Z\d]+=$ `
>
> `传真号码` `^(([0\+]\d{2,3}-)?(0\d{2,3})-)(\d{7,8})(-(\d{3,}))?$`
>
> `护照` `^([a-zA-z]|[0-9]){5,17}$`





































































































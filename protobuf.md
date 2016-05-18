# protobuf 编解码

PB对象的 string 字段 toString() 时，会用UTF8编码, 再转成3位的８进制数输出

"小黄瓜" => "\345\260\217\351\273\204\347\223\234"

有时候日志中仅有编码后的一串数字,需要解码后才能显示原文

## com.google.protobuf.TextFormat 提供了私有的 unescapeText 方法

抽取 unescapeText, 可以实现一个解码方法

例如：unescapeText("\\345\\260\\217\\351\\273\\204\\347\\223\\234")

得到: "小黄瓜"

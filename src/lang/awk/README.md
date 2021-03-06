---
description: AWK、Sed等
---

# AWK & Sed

## AWK

AWK是一种优良的文本处理工具，Linux及Unix环境中现有的功能最强大的数据处理引擎之一。AWK提供了极其强大的功能：可以进行正则表达式的匹配，样式装入、流控制、数学运算符、进程控制语句甚至于内置的变量和函数。

将文件内的每一行以空格分隔，打印每一行的第五列：

```shell
awk '{print $5}' filename
```

通过正则表达式匹配文件内的每一行，然后将行内容以空格分隔，打印每一行的第二列：

```shell
awk '/regexp/ {print $2}' filename

awk '$1 ~ /regexp/ {print $2}' filename
```

指定分隔符，输出每一行的列的数量

```shell
awk -F ',' '{print $NF}' {{filename}}
```

### 语句定义

1. 可以快速的用单引号’ ’，把所有语句写成一行；
2. 也可以用-f 指定文件，文件里可以任意换行，增加可读性和重用性；
3. 所有执行语句用{}括起来，{}的外面是一些高级的东西比如过滤条件；
4. 另外如果打印整列，{print} 可省略不写；

### 列引用

1. $0代表整行所有数据，$1代表第一列\(终于不是程序员数数从0开始了\)；
2. NF是个代表总列数的系统变量，所以$NF代表最后一列，还支持$\(NF-1\)来表示倒数第二列；
3. 还支持列之间的运算，如$NF-$\(NF-1\)是最后两列的值相减；
4. 只写一个print 是 print $0的简写，打印整行所有数据；

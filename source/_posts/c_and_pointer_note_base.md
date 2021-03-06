---
title: 《C和指针》Note之基础
tags: 
    - C
categories: C语言
---
C存在两种不同的环境：`翻译环境`和`执行环境`;
<!-- more --> 
翻译环境是将源代码转换为可执行的机器指令，而执行环境用于实际执行代码。
### 翻译
其中翻译阶段主要包括了`编译`和`链接`两部分。
>__ 编译
将源代码转换为目标代码的过程，在这个过程中包含了`预处理`（预处理相关操作，比如define替换为实际值）和`解析`（判断源代码的意思），在最后生成`目标代码`（机器指令的初步形式）。
#### 链接
链接器会把各个目标文件捆绑起来形成一个可执行程序。在这个过程中会引入c函数库。

### 执行
程序载入到内存中，并初始化在堆栈中没有初始化的变量。

>__ 运行时堆栈
用户保存函数的局部变量和返回值。
#### 静态内存
存储在静态内存中的变量将会在程序执行期间一直保留！

程序的终止可以是`main函数`完成返回，也可以是主动执行了`exit`。

### 一个技巧
如果在使用注释的时候`/**/`嵌套了多层会导致注释失效，这时候我们可以在最外层添加:
```
#if 0
//中间为代码
#endif
```
而且在使用注释的时候并不会把注释掉的部分从源代码中删除，只是不去执行而已，使用`if endif`的话是在逻辑上删除了这一段代码的。
这在后面的预处理器那一节会讲更多。


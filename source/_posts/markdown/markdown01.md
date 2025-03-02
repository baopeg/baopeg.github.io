---
title: markdown基础语法（一）
date: 2025-03-01
tags: ["markdown","基础语法","教程"]
categories: ["技术教程","markdown"]
keywords: ["markdown", "语法", "教程", "基础"]
description: "本文介绍了Markdown的基础语法，包括标题、段落、字体、列表、区块、代码、链接、图片、表格和HTML标签的使用方法。"
cover: /img/markdown01_cover.png
---

# markdown基础语法

> - 参考文章：[菜鸟教程](https://www.runoob.com/markdown/md-tutorial.html)，[markdown指南中文版](https://www.markdown.xyz/basic-syntax/)，[github markdown](https://docs.github.com/cn/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
> - 编辑器推荐：[vscode](https://code.visualstudio.com/),[typora](https://typora.io/)

## 标题

使用 # 号表示标题，数量对应HTML的H1-H6：

```markdown
# H1标题

## H2标题

### H3标题

#### H4标题

##### H5标题

###### H6标题
```

效果图如下：
![标题效果图](标题.png)

## 段落

```markdown
1. 普通段落直接书写，无需缩进,回车也没有关系
2. 换行需要行尾加两个空格或者段落间空一行
```

效果图如下：
![段落效果图](段落.png)

## 字体

```markdown
**粗体文本**  
*斜体文本*  
***粗斜体文本***  
~~删除线文本~~  
```

效果图如下：
![字体效果图](字体.png)

## 列表

### 无序列表

```markdown
- 项目1
    - 子项目1
    - 子项目2

* 项目2

+ 项目3
```

效果图如下：
![无序列表效果图](无序列表.png)

### 有序列表

```markdown
1. 第一项
2. 第二项
    1. 子项1
    2. 子项2
```

效果图如下：
![有序列表效果图](有序列表.png)

## 区块

使用 > 符号表示引用：

```markdown
> 一级引用
>> 嵌套引用
```

效果图如下：
![区块效果图](区块.png)

## 代码

```markdown
行内代码使用反引号：
`print("Hello World")`

代码块使用三个反引号,后面跟随编程语言标识，后面换行再写代码，最后换行再结束。注意在编程语言表示后面添加文件名称
```python hello.py
def hello():
     print("Hello Markdown!")
\```
```

效果图如下：
![代码效果图](代码.png)

## 链接

行内链接：
```markdown
[菜鸟教程](https://www.runoob.com/markdown/md-tutorial.html)
```

效果展示：[菜鸟教程](https://www.runoob.com/markdown/md-tutorial.html)

参考式链接：
```markdown
这个链接用 1 作为网址变量 [Google][1]
这个链接用 runoob 作为网址变量 [Runoob][runoob]
然后在文档的结尾为变量赋值（网址），注意最后分开段落，与文章之间留有一个空行。

[1]: http://www.google.com/
[runoob]: http://www.runoob.com/

```
效果展示：
这个链接用 1 作为网址变量 [Google][1]
这个链接用 runoob 作为网址变量 [Runoob][runoob]
然后在文档的结尾为变量赋值（网址）

[1]: http://www.google.com/
[runoob]: http://www.runoob.com/

## 图片

```markdown
![图片label](图片URL)  # 图片URL可以是本地文件路径，也可以是网络地址，label为图片的描述
举个例子：
本地：![Logo](./logo.png)
网络：![外南街1982](https://p6.itc.cn/q_70/images03/20221220/0806bb5716604a51a0d092dc03ef9a5a.jpeg)
```

效果图如下：
![外南街1982](https://p6.itc.cn/q_70/images03/20221220/0806bb5716604a51a0d092dc03ef9a5a.jpeg)

## 表格

使用 | 分隔列，- 分隔表头：

```markdown
| 左对齐 | 居中对齐 | 右对齐 |
| :----- | :------: | -----: |
| 数据1  |   数据2  |   数据3 |
| 数据4  |   数据5  |   数据6 |
```

效果图如下：

| 左对齐 | 居中对齐 | 右对齐 |
| :----- | :------: | -----: |
| 数据1  |   数据2  |   数据3 |
| 数据4  |   数据5  |   数据6 |

## HTML 标签

Markdown支持直接插入HTML标签：

```markdown
使用<br>强制换行  
<span style="color:red">红色文本</span>
```

> 注意：在大多数Markdown解析器中，HTML标签需要谨慎使用
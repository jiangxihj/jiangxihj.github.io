---
layout: post
title: "github page中Markdown渲染引擎redcarpet使用"
description: "研究github page中Markdown渲染引擎"
category: "Markdown"
tags: [Markdown, 渲染]
---

先来测试[redcarpet官网](https://github.com/vmg/redcarpet)提到的新特性：

* **footnotes | 脚注**

This is a sentence.[^1]

* **table | 表格**


| Item     | Value | Qty   |
| :------- | :---- | :---: |
| Computer | $1600 |  5    |
| Phone    | $12   |  12   |
| Pipe     | $1    |  234  |

* **fenced_code_blocks | 代码段**

```
// Foo
var bar = 0;
```

* **autolink | 自动识别链接**

www.hao123.com

* **disable_indented_code_blocks | 不支持空四格来表示代码段**

    // Foo
    var bar = 0;

* **strikethrough | 文字中间画一条横线代表删除**

this is ~~good~~ bad

* **lax_spacing | 解析Html不需要空行**
<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>

* **space_after_headers | 解析标题需要在#后空一格**

####this is my header

#### this is my header


* **superscript | 上标**

this is the 2^(nd) time

* **underline | 下划线**

This is _underlined_ but this is still *italic*

* **no_intra_emphasis | 单词中下划线不会被解析成带下划线的文本**

foo_bar_baz 

* **highlight | 高亮强调**

This is ==highlighted==

* **quote | 双引号**

This is a "quote"



---
具体使用这些特性的话，只需要修改主文件夹中的_config.yml配置文件，把这些属性都添加进去，我的配置文件是:

```
baseurl: /
markdown: Redcarpet
markdown_ext:  markdown,mkd,mkdn,md
redcarpet:
  extensions: ["no_intra_emphasis", "fenced_code_blocks", "autolink", "tables", "strikethrough", "superscript", "with_toc_data", "footnotes","space_after_headers","highlight","underline","quote","lax_spacing"]
permalink: /:year/:month/:day/:title/
author: HyperHu
pygments: true
safe: true
paginate: 16
auto: true
```
---

补充几个网址：


* [github推荐引擎redcarpet](https://github.com/vmg/redcarpet)
* [一篇好博客:jekyll + markdown使用笔记](http://blog.coloam.com/jekyll/markdown/2013/09/22/markdown-note/)

[^1]: This is a footnote

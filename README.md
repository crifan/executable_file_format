# 可执行文件格式

* 最新版本：`v0.8.3`
* 更新时间：`20231007`

## 简介

介绍常用的可执行文件格式，先是概览；然后是通用内容；接着介绍常见格式，包括早期通用的COFF、Windows的PE、Linux/Android的ELF、macOS/iOS的Mach-O，以及相关的工具，比如查看格式的file，和解析格式的LIEF，且给出具体用法实例，包括解析Mach-O、解析Android的OAT、解析ELF；以及相关子教程。

## 源码+浏览+下载

本书的各种源码、在线浏览地址、多种格式文件下载如下：

### HonKit源码

* [crifan/executable_file_format: 可执行文件格式](https://github.com/crifan/executable_file_format)

#### 如何使用此HonKit源码去生成发布为电子书

详见：[crifan/honkit_template: demo how to use crifan honkit template and demo](https://github.com/crifan/honkit_template)

### 在线浏览

* [可执行文件格式 book.crifan.org](https://book.crifan.org/books/executable_file_format/website/)
* [可执行文件格式 crifan.github.io](https://crifan.github.io/executable_file_format/website/)

### 离线下载阅读

* [可执行文件格式 PDF](https://book.crifan.org/books/executable_file_format/pdf/executable_file_format.pdf)
* [可执行文件格式 ePub](https://book.crifan.org/books/executable_file_format/epub/executable_file_format.epub)
* [可执行文件格式 Mobi](https://book.crifan.org/books/executable_file_format/mobi/executable_file_format.mobi)

## 版权和用途说明

此电子书教程的全部内容，如无特别说明，均为本人原创。其中部分内容参考自网络，均已备注了出处。如发现有侵权，请通过邮箱联系我 `admin 艾特 crifan.com`，我会尽快删除。谢谢合作。

各种技术类教程，仅作为学习和研究使用。请勿用于任何非法用途。如有非法用途，均与本人无关。

## 鸣谢

感谢我的老婆**陈雪**的包容理解和悉心照料，才使得我`crifan`有更多精力去专注技术专研和整理归纳出这些电子书和技术教程，特此鸣谢。

## 其他

### 作者的其他电子书

本人`crifan`还写了其他`150+`本电子书教程，感兴趣可移步至：

[crifan/crifan_ebook_readme: Crifan的电子书的使用说明](https://github.com/crifan/crifan_ebook_readme)

### 关于作者

关于作者更多介绍，详见：

[关于CrifanLi李茂 – 在路上](https://www.crifan.org/about/)

---
title: "misc Email"
categories:
  - Thinking
tags:
  - 学习
last_modified_at: 2019-02-23
toc: true
toc_label: "文章提纲"
---


1.用流量分析软件wireshark追踪IAMP数据包，可以看到发送了一个名为20161008103416509320.7z的邮件附件，文件以Base64格式编码：

N3q8ryccAAQ9AshlwFQFAAAAAAAqAAAAAAAAAOjuWeI83mZQMTuDbrw/ESKoLQCVZl4iDZ8FFWPWaFcXMf...

2.base64解码方法

Base64是网络上最常见的用于传输8Bit字节码的编码方式之一，Base64就是一种基于64个可打印字符来表示二进制数据的方法。定义Base64的RFC文档同样定义了MIME的详细规范。

Base64编码是从二进制到字符的过程，可用于在HTTP环境下传递较长的标识信息，采用Base64编码具有不可读性，需要解码后才能阅读。

简单来说，Base64编码就是将3个字节的信息拆分为4个6位，最高两位补0，形成4个字节的信息。

如：

        abc
ASCII:  97 98 99
Bin:    01100001 01100010 01100011
分组：   011000 010110 001001 100011
补0：    00011000 00010110 00001001 00100011
Oct:    30 26 11 43
查表：   e a L r
 
就这样，就可以实现base64解码。

3.用base64解码法将其解码到文件，打开时提示文件已加密。

4.所以现在要找到解压缩包的密码，再仔细寻找发现，除了发送7z附件，还发送了其他的信息

5.找到一段字符

Fl5266q4PzYXSPdmgzrA

尝试将其作为压缩包的密码，可以打开压缩包，里面有20161008103416509320.pdf文件，打开后未发现所需要的flag

6.题目暂未解出，应该进一步探索pdf文件。

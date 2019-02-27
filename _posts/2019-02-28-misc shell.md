---
title: "misc shell"
categories:
  - Thinking
tags:
  - 学习
last_modified_at: 2019-02-23
toc: true
toc_label: "文章提纲"
---
查了很多流量分析的资料...不得解  然后看到其中一篇是说要用base64解码 ，然后开始关注data部分，每一行的data都要注意，题目要求关注整个流量，然后就追踪TCP流。

1.使用WireShark打开文件


2.在7号TCP报文的DATA字段发现

ls -la


3.在9号TCP报文的DATA字段发现

-rw-rw-r-- 1 user user 28 Feb 5 07:57 flag.txt


4.在15号TCP报文的DATA字段发现

cat ./flag.txt base64


5.在28号TCP报文的DATA字段发现

ZmxhZ3tyZXZlcnNlX3NoZWwxbDFsbGwxbH0KCg==

6.用base64解码得flag

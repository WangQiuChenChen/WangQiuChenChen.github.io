---
title: "misc  Another01Gam"
categories:
  - Thinking
tags:
  - 学习
last_modified_at: 2019-02-23
toc: true
toc_label: "文章提纲"
---



  1.根据题目要求，是将TXT文件中的0和1组成一个正方形，用MATLAB编程生成图片
  
  2.首先根据01字符的个数和题目提示判断应为37x37的图像，又根据提示图象应该是一个二维码图片，所以应为黑白两色。然后将0视为黑色像素(0, 0, 0)，1视为白色像素(255, 255, 255)，生成二维码图片01game.png

    用微信扫得到字符串

    1100110110110011000011100111111101111110010110000101010110111111001011100111010011111010111101111111000011100010011000011101011110
  
  3.题目提示是统计字符串长度，可以当作 ASCII 编程，所以判断应该是将此字符串用ASCII解码得flag
  


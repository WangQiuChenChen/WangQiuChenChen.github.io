---
title: "Web Calculator相关知识学习"
categories:
  - Thinking
tags:
  - 学习
last_modified_at: 2019-02-23
toc: true
toc_label: "文章提纲"
---


## 发送请求
　　
  
    根据题目Web Calculator中提供的Requests官方文档，学习了如下内容，并以Web Calculator题目做练习

    
    import requests

    r = requests.get(url)   
    r = requests.post(url)
    r = requests.put(url)
    r = requests.delete(url)
    r = requests.head(url)
    r = requests.options(url)

    r = requests.get(url='http://121.42.176.204:23331/calculator/')
    
    print(r.text)
    
    然后就可以输出网页HTML代码：
    
    
    <!DOCTYPE html>
<html>
    <head>
        <title>Calculator</title>
        <style type="text/css">
                .line_input{
                        border-width: 1px;
                        border-bottom: solid;
                        border-top: none;
                        border-left: none;
                        border-right: none;
                        border-width: 1px;
                        text-align: center;
                        outline: none;
                        margin: 0 1em;
                }
        </style>
    </head>
    <body>
        <center>
            <h1>Yet Another Calculator</h1>
            <p>Let's play a game. Please work on this math problem, and make it in 1.5 seconds.</p>
            <form action="" method="GET"><span id="exp">5160526 + 81114644008 - 158998 = </span>
            <input name="answer" type="text" autofocus class="line_input" /><input type="submit" /></form>
        </center>
    </body>
</html>


可以得到要计算的式子为：5160526 + 81114644008 - 158998，计算结果为35701914696

然后面临要传这个结果参数的问题。

## 传递参数

     百度发现Requests 允许使用 params 关键字参数，以一个字符串字典来提供这些参数，还可以将一个列表作为值传入
    
     尝试使用answer=35701914696作为payload向题目中传递参数

     payload = {'answer': '35701914696'}
     r = requests.get('http://121.42.176.204:23331/calculator/', params=payload)
     print(r.url)
     print(r.text)

    输出内容是

     Expression has not been generated.

     所以此法无效。
   

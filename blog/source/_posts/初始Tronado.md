---
title: 初始Tronado
date: 2018-08-07 11:17:42
tags:
---
# 初识Tornado
## 关于Tornado
Tornado发布于2009年9月，是Facebook从当时收购的FriendFeed的实时信息服务开发而来。
摘抄自Tornado的官方文档：  
Tornado is a Python web framework and asynchronous networking library, originally developed at FriendFeed. By using non-blocking network I/O, Tornado can scale to tens of thousands of open connections, making it ideal for long polling, WebSockets, and other applications that require a long-lived connection to each user.   
Tornado是一个Python Web框架和异步网络库，最初是在FriendFeed上开发的。通过使用非阻塞网络I / O，Tornado可以扩展到数万个开放连接，使其成为长轮询，WebSockets和其他需要与每个用户建立长期连接的应用程序的理想选择。   
因此确定Tornado的两个应用方向，Python的Web框架和异步网络库。这都得利于Tornado的非阻塞网络模型。 
## 安装Tornado  
执行命令
```
pip install tornado
```
## Hello World for Tornado
```
import tornado.ioloop # tornado核心库，提供了tornado的webserver
import tornado.web # 

class MainHandler(tornado.web.RequestHandler):
    def get(self):
        self.write("Hello, world")

def make_app():
    return tornado.web.Application([
        (r"/", MainHandler),
    ])

if __name__ == "__main__":
    app = make_app()
    app.listen(8888)
    tornado.ioloop.IOLoop.current().start()
```

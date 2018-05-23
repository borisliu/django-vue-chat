# djang-vue-chat
使用Django Channels构造的一个聊天程序，分为前后台，前台界面采用Framework7-Vue构建，后台界面采用Element-UI构建，一个后台可以和多个前台同时聊天。

## 项目介绍
很多网站都会用到在线客服这个功能，软件基于Django和WebSocket制作，可以完成多对一即时聊天，即客服一个端(service)，多个用户可以和唯一的客服聊天,当然如果你登录两个客服端，他们都能同时收到客户发来的信息。程序运行需要Django，如果不会可以看我的另外一篇教程[从Python到Django入门教程](https://borisliu.gitbooks.io/from-python-to-django/)

## 软件架构
Django，Framework7-vue，Vue，Plain HTMl(no webpack、npm、babel)，Element-UI
程序工作原理：
  每个客户都有自己的socketId，客服被分在同一个命名空间（service分组），客户发信息，服务器转发给server分组中所有成员(所有客服)，并记录好发来信息的客户sockeId，客服回复信息到指定客户就是通过socketId来完成。具体细节看代码注释。


## 安装教程

1. 下载redis并运行
2. clone到本地
3. 安装Python3 > 3.5
4. virtualenv
5. python manage.py runserver 0.0.0.0:8000

## 使用说明

1. 访问http://localhost:8000/service.html启动服务端
2. 打开一个或多个http://localhost:8000/client.html启动客户端
3. 可以一对多聊天

## 截图

运行之后，通过浏览器进入页面[http://localhost:8000/service.html]()，看到一个空的服务端页面:

![](https://raw.github.com/borisliu/django-vue-chat/master/screenshot/service1.png) 

再通过浏览器访问[http://localhost:8000/client.html]()，看到一个空的客户端页面：

![](https://raw.github.com/borisliu/django-vue-chat/master/screenshot/client1.png)

在客户端输入一些文字，可以看到客户端和服务端开始了聊天。

![](https://raw.github.com/borisliu/django-vue-chat/master/screenshot/client2.png)

![](https://raw.github.com/borisliu/django-vue-chat/master/screenshot/service2.png)

再通过浏览器访问[http://localhost:8000/client.html]()，打开另一个客户端页面，说一些话，可以看到服务端多了一个菜单，可以实现一对多聊天：

![](https://raw.github.com/borisliu/django-vue-chat/master/screenshot/service3.png)

## 参与贡献

1. Fork 本项目
2. 新建 Feat_xxx 分支
3. 提交代码
4. 新建 Pull Request


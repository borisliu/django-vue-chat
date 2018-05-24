# Djang-Vue-Chat

使用Django Channels和Vue技术构造的一个聊天程序，分为前后台，前台界面采用Framework7-Vue构建，后台界面采用Element-UI构建，一个后台可以和多个前台同时聊天。

## 项目介绍

很多网站都会用到在线客服这个功能，软件基于Django Channels和WebSocket制作，可以完成多对一即时聊天，即客服一个端(service)，多个用户可以和唯一的客服聊天,当然如果你登录两个客服端，他们都能同时收到客户发来的信息。程序运行需要Django，如果不会可以看我的另外一篇教程[从Python到Django入门教程](https://borisliu.gitbooks.io/from-python-to-django/)

## 技术栈

- 应用框架: Django，使用了Channels技术
- 前端: Framework7-vue(采用静态HTML5实现，没有Webpack, Babel和npm)
- 后端: Element-UI(采用静态HTML5实现，没有Webpack, Babel和npm)
- 通信协议: WebSocket

## 工作原理

每个客户都有一个自己的标识（Client ID），由Unix时间戳加上一位随机数构成。所有的客户和客服人员都在一个通讯组（Channels Group）中，每条消息会发送给组内的所有成员，客户根据自己ID展示消息。客服人员通过指定的ID回复给指定的客户。

## 安装说明

### 第一步：下载并启动Redis服务器

到[Redis官网](https://redis.io/)下载并安装好Redis服务器，然后启动它，采用默认的配置即可。

### 第二步：Clone项目到本地

```bash
git clone https://github.com/borisliu/django-vue-chat.git
cd django-vue-chat
```

### 第三步：确认Python版本为3.5+

```bash
python --version
```

### 第四步：设置虚拟环境virtualenv

```bash
virtualenv venv
source venv/bin/activate
pip install -r requirements-linux.txt
```
如果是Windows环境则安装requirements-win.txt

### 第五步：启动程序

```bash
python manage.py runserver
```

## 使用说明

1. 访问[http://localhost:8000/service.html]()打开服务端。
2. 打开一个或者多个[http://localhost:8000/client.html]()作为客户端。
3. 然后你就可以开始聊天啦！

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
2. 新建 Feature_xxx 分支
3. 提交代码
4. 新建 Pull Request


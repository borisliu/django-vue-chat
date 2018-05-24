# Djang-Vue-Chat
A simple chat room based on Django Channels and Vue.Using Framework7-Vue as Frontend, Element-UI as Backend. One - to - one chat and one - to - many group chat modes are supported.

[中文README.md](/README-zh.md)

## Use Case
Many sites will use online customer service.The project is based on Django Channels, using WebSocket to complete the real-time chat.Multiple users can chat with the only one customer service, of course, if you login two customer service end, They can all receive information from customers at the same time. Program running requires Django, which you can refer to my another tutorial [From Python to Django](https://borisliu.gitbooks.io/from-python-to-django/)

## Tech Stack
- App Framework: Django and Channels
- Frontend: Framework7-vue(Plain HTML5.without Webpack, Babel and npm)
- Backend: Element-UI(Plain HTML5.without Webpack, Babel and npm)
- Communication Protocol: WebSocket

## Operating mechanism
Each customer has its own identity (client ID), consisting of a Unix timestamp plus a random number.All customer and customer service personnel are in a distribution group (channels group), each message is sent to all members within the group, and the customer displays the message based on its own ID.The customer service person responds to the specified customer by the specified ID.


## Installation

### Step 1: Download and Install Redis Server

Visit [Redis Homepage](https://redis.io/) to download and install a redis server. Then run the server using default configuration.

### Step 2: Clone this project

```bash
git clone https://github.com/borisliu/django-vue-chat.git
cd django-vue-chat
```

### Step 3: Make sure the version of Python is 3.5+

```bash
python --version
```

### Step 4: Set up the virtualenv

```bash
virtualenv venv
source venv/bin/activate
pip install -r requirements-linux.txt
```
If you are using Windows, install the requirements with `requirements-win.txt`

### Step 5: Start up the program
```bash
python manage.py runserver
```

## Usage

1. Visit[http://localhost:8000/service.html]() to have your customer service.
2. Open one or many [http://localhost:8000/client.html]() to have your customers.
3. Then you can chat!

## Screenshot

After you run the program, you can visit[http://localhost:8000/service.html]() to see an empty service page.

![](https://raw.github.com/borisliu/django-vue-chat/master/screenshot/service1.png) 

Visit [http://localhost:8000/client.html]() to see a client page.

![](https://raw.github.com/borisliu/django-vue-chat/master/screenshot/client1.png)

Type some words in the client page,then you can chat with your customer service.

![](https://raw.github.com/borisliu/django-vue-chat/master/screenshot/client2.png)

![](https://raw.github.com/borisliu/django-vue-chat/master/screenshot/service2.png)

Open another browser to visit [http://localhost:8000/client.html](). You can get a new client page. Say something, you will see the new menu item in service page.

![](https://raw.github.com/borisliu/django-vue-chat/master/screenshot/service3.png)

## How to contrubite

1. Fork the source code in your own github repo.
2. Create a new branch named Feature_xxx.
3. After finish, commit your source code to your own repo.
4. Commit a Pull Request to the main repo.


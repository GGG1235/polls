# polls

***

环境:

Django2.1.2

Python3.7.0

PyCharm 2018.3.5 (Professional Edition)

macOS 10.14.3

### 创建项目

```
django-admin startproject polls
```

 startproject 创建了:
 
 ```
 polls/
    manage.py
    polls/
        __init__.py
        settings.py
        urls.py
        wsgi.py
 ```

>>> 这些目录和文件的用处是：
>>> 
>>> 最外层的:file: mysite/ 根目录只是你项目的容器， Django 不关心它的名字，你可以将它重命名为任何你喜欢的名字。
>>> manage.py: 一个让你用各种方式管理 Django 项目的命令行工具。你可以阅读 django-admin and manage.py 获取所有 manage.py 的细节。
>>> 里面一层的 mysite/ 目录包含你的项目，它是一个纯 Python 包。它的名字就是当你引用它内部任何东西时需要用到的 Python 包名。 (比如 mysite.urls).
>>> mysite/__init__.py：一个空文件，告诉 Python 这个目录应该被认为是一个 Python 包。如果你是 Python 初学者，阅读官方文档中的 更多关于包的知识。
>>> mysite/settings.py：Django 项目的配置文件。如果你想知道这个文件是如何工作的，请查看 Django settings 了解细节。
>>> mysite/urls.py：Django 项目的 URL 声明，就像你网站的“目录”。阅读 URL调度器 文档来获取更多关于 URL 的内容。
>>> mysite/wsgi.py：作为你的项目的运行在 WSGI 兼容的Web服务器上的入口。阅读 如何使用 WSGI 进行部署 了解更多细节。

### 数据库配置

在settings.py中设置DATABASES 'default' 项目中的一些键值：ENGINE -- 可选值有```django.db.backends.sqlite3```,```django.db.backends.postgresql```,```django.db.backends.mysql```,或 ```django.db.backends.oracle```。其它 可用后端。
NAME - 数据库的名称。如果使用的是 SQLite，数据库将是你电脑上的一个文件，在这种情况下， NAME 应该是此文件的绝对路径，包括文件名。默认值 ```os.path.join(BASE_DIR, 'db.sqlite3')``` 将会把数据库文件储存在项目的根目录。
如果你不使用 SQLite，则必须添加一些额外设置，比如 USER 、 PASSWORD 、 HOST 等等。

通过终端运行```python manage.py migrate```来创建一些表.

>>> 这个 migrate 命令检查 INSTALLED_APPS 设置，为其中的每个应用创建需要的数据表，至于具体会创建什么，这取决于你的 mysite/settings.py 设置文件>>> 和每个应用的数据库迁移文件（我们稍后会介绍这个）。这个命令所执行的每个迁移操作都会在终端中显示出来。如果你感兴趣的话，运行你数据库的命令行工具，并输>>> 入 \dt (PostgreSQL)， SHOW TABLES; (MySQL)， .schema (SQLite)或者 SELECT TABLE_NAME FROM USER_TABLES; (Oracle) 来看看 Django >>> 到底创建了哪些表。

### 激活模型

通过终端运行```python manage.py makemigrations polls```来激活模型.

>>> 通过运行 makemigrations 命令，Django 会检测你对模型文件的修改（在这种情况下，你已经取得了新的），并且把修改的部分储存为一次 迁移。
>>>
>>> 迁移是 Django 对于模型定义（也就是你的数据库结构）的变化的储存形式 - 没那么玄乎，它们其实也只是一些你磁盘上的文件。如果你想的话，你可以阅读一下你>>> 模型的迁移数据，它被储存在 polls/migrations/0001_initial.py 里。别担心，你不需要每次都阅读迁移文件，但是它们被设计成人类可读的形式，这是为了>>> 便于你手动修改它们。
>>> 
>>> Django 有一个自动执行数据库迁移并同步管理你的数据库结构的命令 - 这个命令是 migrate，我们马上就会接触它 - 但是首先，让我们看看迁移命令会执行哪些 >>> SQL 语句。sqlmigrate 命令接收一个迁移的名称，然后返回对应的 SQL: ```python manage.py sqlmigrate polls 0001```

### 截图 : 

<img src="https://github.com/GGG1235/polls/blob/master/images/index.png" width="375" alt="index">

<img src="https://github.com/GGG1235/polls/blob/master/images/context.png" width="375" alt="内容">

<img src="https://github.com/GGG1235/polls/blob/master/images/admin-login.png" width="375" alt="后台登录">

<img src="https://github.com/GGG1235/polls/blob/master/images/admin-index.png" width="375" alt="后台主页">

<img src="https://github.com/GGG1235/polls/blob/master/images/question.png" width="375" alt="管理问题">

<img src="https://github.com/GGG1235/polls/blob/master/images/question_1.png" width="375" alt="问题详情">

<img src="https://github.com/GGG1235/polls/blob/master/images/user.png" width="375" alt="管理用户">

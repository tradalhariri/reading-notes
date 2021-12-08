# Django Custom User

- Django ships with a built-in User model for authentication and if you'd like a basic tutorial on how to implement log in, log out, sign up and so on see the Django Login and Logout tutorial for more.

- a custom user model provides more flexibility down the line so, as a general rule, always use a custom user model for all new Django projects.


## Setup


- To start, create a new Django project from the command line.
  - create and navigate into a dedicated directory
  - install Django
  - make a new Django project called `config`
  - make a new app `accounts`
  - start the local web server

```s
$ cd ~/Desktop
$ mkdir accounts && cd accounts
$ pipenv install django~=3.1.0
$ pipenv shell
(accounts) $ django-admin.py startproject config .
(accounts) $ python manage.py startapp accounts
(accounts) $ python manage.py runserver
```

> It's important to wait run `migrate` until after we've created our new custom user model before doing so.


![](https://learndjango.com/static/images/django31_welcome.png)

## AbstractUser vs AbstractBaseUser


- There are two modern ways to create a custom user model in Django:
  - AbstractUser
  - AbstractBaseUser

>  In both cases we can subclass them to extend existing functionality however `AbstractBaseUser` requires much, much more work. Seriously, don't mess with it unless you really know what you're doing.


## Custom User Model

- Creating our initial custom user model requires four steps:
  - update `config/settings.py`
  - create a new `CustomUser` model
  - create new `UserCreation` and `UserChangeForm`
  - update the admin

## Superuser

> It's helpful to create a superuser that we can use to log in to the admin and test out log in/log out



# DjangoX


## Installation


> DjangoX can be installed via Pip, Pipenv, or Docker depending upon your setup.
> 
>  To start, clone the repo to your local computer and change into the proper directory.

```s
$ git clone https://github.com/wsvincent/djangox.git
$ cd djangox
```
**Pip**
```s
$ python3 -m venv djangox
$ source djangox/bin/activate
(djangox) $ pip install -r requirements.txt
(djangox) $ python manage.py migrate
(djangox) $ python manage.py createsuperuser
(djangox) $ python manage.py runserver
# Load the site at http://127.0.0.1:8000

```
**Pipenv**
```s
$ pipenv install
$ pipenv shell
(djangox) $ python manage.py migrate
(djangox) $ python manage.py createsuperuser
(djangox) $ python manage.py runserver
# Load the site at http://127.0.0.1:8000

```
**Docker**
```s

$ docker build .
$ docker-compose up -d
$ docker-compose exec web python manage.py migrate
$ docker-compose exec web python manage.py createsuperuser
# Load the site at http://127.0.0.1:8000

```
> For Docker, the INTERNAL_IPS configuration in config/settings.py must be updated to the following:

```s

# config/settings.py
# django-debug-toolbar
import socket
hostname, _, ips = socket.gethostbyname_ex(socket.gethostname())
INTERNAL_IPS = [ip[:-1] + "1" for ip in ips]

```

### Setup

```s
# Run Migrations
(djangox) $ python manage.py migrate

# Create a Superuser
(djangox) $ python manage.py createsuperuser

# Confirm everything is working:
(djangox) $ python manage.py runserver

# Load the site at http://127.0.0.1:8000
```

### References
[Django Custom User](https://learndjango.com/tutorials/django-custom-user-model)
<br>
[DjangoX](https://github.com/wsvincent/djangox)
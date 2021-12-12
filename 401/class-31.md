# A Beginner's Guide to Docker

![docker](https://miro.medium.com/max/770/0*5zQfr6j2fAeNPy-H.png)

## What is Docker?

> Docker its a tool to isolate the whole development environment you are working on , programming language, software packages, databases, and more.
> Docker is a way to run Linux containers.

## Why Docker?
* Docker is an open source containerization platform. It enables developers to package applications into containers—standardized executable components combining application source code with the operating system (OS) libraries and dependencies required to run that code in any environment.



## Containers Vs Virtual Environment
* Virtual environments are used to isolate Python software packages locally.
* But Docker is used to isolate the whole development environment.
* docker share the base operating system with all containers.
* Virtualization creates separate OS for each application.

## Docker Guide 
* for installation and practice docker refer to ... 
[Docker guide](https://wsvincent.com/beginners-guide-to-docker/)

# Django for APIs - Library Website
## Chapter 2: Library Website and API

* Django REST Framework works alongside the Django web framework to create web APIs. We cannot build a web API with only Django Rest Framework; it always must be added to a project after Django itself has been installed and configured.

## How Django REST Framework works ?


* Django REST Framework is added just like any other third-party app.
  
1. first install it: 

    `$ pipenv install djangorestframework~=3.11.0`

2. Add it to the installed apps in settings file
```python
# config/settings.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # 3rd party
    'rest_framework',

    # Local
    'books',
    'api', # new
]
```


3. The best practice is to create  app to hold API info 
>`python manage.py startapp api`
4. add url file to api app:
```python
# config/urls.py
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('api/', include('api.urls')), # new
    path('', include('books.urls')),
]
```
5. add api route to the project urls
```python
   # config/urls.py
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('api/', include('api.urls')), # new
    path('', include('books.urls')),
]
```
6. add view file to the api app 

```python
# api/views.py
from rest_framework import generics

from books.models import Book
from .serializers import BookSerializer


class BookAPIView(generics.ListAPIView):
    queryset = Book.objects.all()
    serializer_class = BookSerializer
```
7. use the view in url file in api app

```python
from django.urls import path
from .views import BookAPIView
urlpatterns = [
    path('', BookAPIView.as_view()),
]
```
8. create serializer file in api app

* serializer converts the data to json which is easy to consume over the internet.
  
```python
# api/serializers.py
from rest_framework import serializers

from books.models import Book


class BookSerializer(serializers.ModelSerializer):
    class Meta:
        model = Book
        fields = ('title', 'subtitle', 'author', 'isbn')
```

![](https://djangoforapis.com/assets/images/02_book_api.png)
<br>

### References
[Beginner’s Guide to Docker](https://wsvincent.com/beginners-guide-to-docker/)
<br>

[Django for APIs - Library Website](https:/djangoforapis.com/library-website-and-api/)






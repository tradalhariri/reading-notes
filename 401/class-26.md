# Intro to Django
## what is Django ?
> Django is a high-level Python web framework that enables rapid development of secure and maintainable websites. Built by experienced developers, Django takes care of much of the hassle of web development, so you can focus on writing your app without needing to reinvent the wheel. It is free and open source, has a thriving and active community, great documentation, and many options for free and paid-for support.

## Object-relational mapper

* Django is based on MVT (Model-View-Template)

> A model is the single, definitive source of information about your data.

> It contains the essential fields and behaviors of the data you’re storing.

> Generally, each model maps to a single database table.

- The basics:
  - Each model is a Python class that subclasses django.db.models.Model.
  - Each attribute of the model represents a database field.

```python
from django.db import models

class Person(models.Model):
    first_name = models.CharField(max_length=30)
    last_name = models.CharField(max_length=30)
```

> By default, Django gives each model an auto-incrementing primary key with the type specified per app in AppConfig.default_auto_field or globally in the DEFAULT_AUTO_FIELD setting.

## URLs and views

> To design URLs for an app, you create a Python module informally called a URLconf (URL configuration). This module is pure Python code and is a mapping between URL path expressions to Python functions (your views).

* How Django processes a request

<br>

- When a user requests a page from your Django-powered site, this is the algorithm the system follows to determine which Python code to execute:
  - Django determines the root `URLconf` module to use. Ordinarily, this is the value of the `ROOT_URLCONF` setting, but if the incoming HttpRequest object has a `urlconf` attribute (set by middleware), its value will be used in place of the `ROOT_URLCONF` setting.
  - Django loads that Python module and looks for the variable `urlpatterns`. This should be a sequence of `django.urls.path()` and/or `django.urls.re_path()` instances.
  - Django runs through each URL pattern, in order, and stops at the first one that matches the requested URL, matching against `path_info`.
  - Once one of the URL patterns matches, Django imports and calls the given view, which is a Python function (or a class-based view). The view gets passed the following arguments:
    - An instance of `HttpRequest`.
    - If the matched URL pattern contained no named groups, then the matches from the regular expression are provided as positional arguments.
    - The keyword arguments are made up of any named parts matched by the path expression that are provided, overridden by any arguments specified in the optional kwargs argument to `django.urls.path()` or `django.urls.re_path()`.
  - If no URL pattern matches, or if an exception is raised during any point in this process, Django invokes an appropriate error-handling view. See Error handling below.

## Templates

* A Django template is a text document or a Python string marked-up using the Django template language.
```html
<html>
  <head>
    <title>Band Listing</title>
  </head>
  <body>
    <h1>All Bands</h1>
    <ul>
    {% for band in bands %}
      <li>
        <h2><a href="{{ band.get_absolute_url }}">{{ band.name }}</a></h2>
        {% if band.can_rock %}<p>This band can rock!</p>{% endif %}
      </li>
    {% endfor %}
    </ul>
  </body>
</html>
```

## Forms


#### HTML forms
* Django provides a powerful form library that handles rendering forms as HTML.
* validating user-submitted data
* converting that data to native Python types. 
* Django also provides a way to generate forms from your existing models and use those forms to create and update data.

```python
from django import forms

class BandContactForm(forms.Form):
    subject = forms.CharField(max_length=100)
    message = forms.CharField()
    sender = forms.EmailField()
    cc_myself = forms.BooleanField(required=False)
```

## Authentication


* Django comes with a full-featured and secure authentication system.
* It handles user accounts, groups, permissions and cookie-based user sessions.
* This lets you easily build sites that allow users to create accounts and safely log in/out.

```python
from django.contrib.auth.decorators import login_required
from django.shortcuts import render

@login_required
def my_protected_view(request):
    """A view that can only be accessed by logged-in users"""
    return render(request, 'protected.html', {'current_user': request.user})
```
## Admin

* One of the most powerful parts of Django is its automatic admin interface.
* It reads metadata in your models to provide a powerful and production-ready interface that content producers can immediately use to start managing content on your site.
* It’s easy to set up and provides many hooks for customization.

```python
from django.contrib import admin
from bands.models import Band, Member

class MemberAdmin(admin.ModelAdmin):
    """Customize the look of the auto-generated admin for the Member model"""
    list_display = ('name', 'instrument')
    list_filter = ('band',)

admin.site.register(Band)  # Use the default options
admin.site.register(Member, MemberAdmin)  # Use the customized options
```

## Internationalization

> Django offers full support for translating text into different languages, plus locale-specific formatting of dates, times, numbers, and time zones. It lets developers and template authors specify which parts of their apps should be translated or formatted for local languages and cultures, and it uses these hooks to localize web applications for particular users according to their preferences.

```python
from django.shortcuts import render
from django.utils.translation import gettext

def homepage(request):
    """
    Shows the homepage with a welcome message that is translated in the
    user's language.
    """
    message = gettext('Welcome to our site!')
    return render(request, 'homepage.html', {'message': message})
```

## Security

- Django provides multiple protections against:
  - Clickjacking
  - Cross-site scripting
  - Cross Site Request Forgery (CSRF)
  - SQL injection
  - Remote code execution


# How Django Works Behind the Scenes


* Django is a Python-based web framework used by millions of developers and billions of consumers through popular apps like Instagram.

* It is open source, meaning the code is available for free on Github and can be downloaded onto any developer’s computer and used alongside the official documentation.

* Django was originally developed at the Lawrence Journal-World newspaper by Adrian Holovaty, Simon Willison, and Jacob Kaplan-Moss.


- Almost all popular open source packages have some degree of funding involved, typically in one of three forms:
  - Corporate Sponsor : funded by company (React Facebook)
  - Solo  : funded by person
  - Non-profit : like Django

* Django Software Foundation

> The `DSF` supports and maintains Django in a number of capacities.

> The largest expense, by far, is the Fellows Program, paid contractors who triage tickets, manage releases, and generally perform the unsexy but necessary work needed to keep Django on track.


* Technical Organization

> The `DSF` handles legal, financial, and administrative matters for Django. But there is a separate organizational structure for the technical team.

### References
[https://www.djangoproject.com/start/](https://www.djangoproject.com/start/)
[How Django Works Behind the Scenes](https://wsvincent.com/how-django-works-behind-the-scenes/)
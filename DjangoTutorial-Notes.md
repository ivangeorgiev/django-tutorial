```bash
$ py -3.9 -m venv .venv39
$ source .venv39/Scripts/activate
$ pip install django djangorestframework
$ python -m django --version
3.2.5
# Create project
$ django-admin startproject mysite
# Try the devault website
$ cd mysite
$ python manage.py runserver
# To run at another port
$ python manage.py runserver 8080
# Listen on specific IP:Port
# 0 is shortcut for 0.0.0.0
$ python manage.py runserver 0:8000
# Create app
$ python manage.py startapp polls
```



## Tutorial 1 - Create project and app

https://docs.djangoproject.com/en/3.2/intro/tutorial01/



## Tutorial 2 - Database and Models

https://docs.djangoproject.com/en/3.2/intro/tutorial02/



## Tutorial 3 - Views

https://docs.djangoproject.com/en/3.2/intro/tutorial03/



## Tutorial 4 - Forms

https://docs.djangoproject.com/en/3.2/intro/tutorial04/



## Tutorial 5 - Writing Tests

https://docs.djangoproject.com/en/3.2/intro/tutorial05/



## Tutorial 6 - Manage Static Files

https://docs.djangoproject.com/en/3.2/intro/tutorial06/

**django.contrib.staticfiles**



### Handle Static Files with Whitenoise

Have a look at [Whtienoise documentation](https://whitenoise.evans.io/en/stable/index.html).

Install whitenoise:

```bash
$ pip install whitenoise
```

Modify `settings.py` - add WhiteNoise to the `MIDDLEWARE` list, above all other middleware apart from Django’s [SecurityMiddleware](https://docs.djangoproject.com/en/stable/ref/middleware/#module-django.middleware.security):

```python
MIDDLEWARE = [
  # 'django.middleware.security.SecurityMiddleware',
  'whitenoise.middleware.WhiteNoiseMiddleware',
  # ...
]
```

Add static root at the end of `settings.py`:

```python
STATIC_ROOT = BASE_DIR / 'staticfiles'
```

Make sure the directory exists. Consider adding it to `.gitgnore` file.

As part of deploying your application you’ll need to run `./manage.py collectstatic` to put all your static files into `STATIC_ROOT`. (If you’re running on Heroku then this is done automatically for you.)

Make sure you’re using the [static](https://docs.djangoproject.com/en/stable/ref/templates/builtins/#std:templatetag-static) template tag to refer to your static files, rather that writing the URL directly. For example:

```
{% load static %}
<img src="{% static "images/hi.jpg" %}" alt="Hi!" />

<!-- DON'T WRITE THIS -->
<img src="/static/images/hi.jpg" alt="Hi!" />
```

For further details see the Django [staticfiles](https://docs.djangoproject.com/en/stable/howto/static-files/) guide.

More details on whitenoise you can find in the [documentation](https://whitenoise.evans.io/en/stable/django.html).

## Tutorial 7 - Customizing Django Admin

https://docs.djangoproject.com/en/3.2/intro/tutorial07/



## How to write reusable code

https://docs.djangoproject.com/en/3.2/intro/reusable-apps/






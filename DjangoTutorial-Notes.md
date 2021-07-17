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



## Tutorial 2 - Database and Models



## Tutorial 3 - Views



## Tutorial 4 - Forms



## Tutorial 5 - Writing Tests



## Tutorial 6 - Manage Static Files


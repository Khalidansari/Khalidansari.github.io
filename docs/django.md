
# Django

## Basic setup

1. Install Python

2. Install virtual environment e.g. venv or pipenv

3. Install django

4. Create django project - django-admin startproject myproj

5. Check to seee if it works by cding to it and then running the following - python manage.py runserver

6. Create Django app - django-admin startapp hello

7. Add the above to settings.py so that the project is aware of this new app.

8. Open the views.py of app (in this case it is hello app) and add import statements and a method to handle the request as follows:

``` python
from django.shortcuts import render
from django.http import HttpResponse

# Create your views here.
def myView(request):
        return HttpResponse("Hello World")
```

9. Update the urls.py to map the url pattern with the view

``` python
from hello.views import myView

urlpatterns = [
    path('admin/', admin.site.urls),
    path('hello', myView),
]
```

## End to end visualization of request response

1. URL requested - /saysomething
2. It comes to django. Routing is handled by urls.py. It looks for a entry corresponding to /saysomething and forwards it to the method mapped there
3. That Method handles the request

## Structure of project

```
myproj
  __init__.py
  admin.py
  apps.py
  models.py
  tests.py
  views.py
  hello
      __init__.py
      settings.py
      urls.py
      wsgi.py
db.sqlite3
manage.py
Pipfile
Pipfile.lock
```

# Django Tutorial

[source](https://www.youtube.com/watch?v=rA4X73E_HV0&list=PL39pssg07dpDJas1vxb7Dyw5f8SkAw6c-)

_Lesson 1_

## Setup

**Virtual environment**

Install pip: `sudo apt-get install python3-pip`

Install virtualenv using pip3: `sudo pip3 install virtualenv`

Create a virtual environment: `virtualenv venv`

Create virtualenv using Python3: `virtualenv -p python3 myenv`

Use a Python interpreter of your choice: `virtualenv -p /usr/bin/python2.7 venv`

Activate your virtual environment: `source venv/bin/activate`

To deactivate: `deactivate`

---

Create a new virtual environment for our website:

```
virtualenv -p /usr/bin/python3.8 DjangoWebsite@3.8
```

To active the virtual environment:

```
source DjangoWebsite@3.8/bin/activate
```

_Lesson 2_

To start server: `python manage.py runserver`

To serve a new homepage we do the following:

1. Add a new http response function in `views.py`

```py
from django.http import HttpResponse

def index(request):
    return HttpResponse("Homepage!")
```

2. Add a new route to `urls.py`

```python
from . import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.index, name="index"),
]
```

stopped at 13:20
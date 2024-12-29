# Ex03 Time Table
# Date: 17/11/2024
# AIM
To write a html webpage page to display your slot timetable.

# ALGORITHM
## STEP 1
Create a Django-admin Interface.

## STEP 2
Create a static folder and inert HTML code.

## STEP 3
Create a simple table using <table> tag in html.

## STEP 4
Add header row using `<th>` tag.

## STEP 5
Add your timetable using `<td>` tag.

## STEP 6
Execute the program using runserver command.

# PROGRAM
first.html
```
<html>
<head>
<title>TIME TABLE</title>     
<style>
 th{
          color: black;
          background-color: lightskyblue ;
          width: 800px;        
     }
     td{
          color: black;
          background-color: darkturquoise;
          
     }
     table{
          border-collapse: collapse;
          margin-top: 40px;
          color: rgb(0, 0, 0);
          font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
          font-size:medium;
     }
</style>
</head>
<body>
        {% load static %}
     <img src="{% static 'images/SEC_LOGO.png' %}">
<table border="10px"width="1300"cellpadding="20px">
<tr>
<th>Day</th>
<th>8-10</th>
<th>10-12</th>
<th>12-1</th>
<th>1-3</th>
<th>3-5</th>
</tr>
<tr>
<th>Monday</th>
<td>Digital Electrics</td>
<td>Web development</td>
<th rowspan="7" style="writing-mode: vertical-rl;">LUNCH</th>
<td>Physics</td>
<td></td>
</tr>
<tr>
<th>Tuesday</th>
<td></td>
<td>Data Science</td>
<td>Digital Electronics</td>
<td></td> 
</tr>
<tr>
<th>Wednesday</th>
<td></td>
<td>IOT</td>
<td></td>
<td></td>
</tr>
<tr>
<th>Thursday</th>
<td>Physics</td>
<td></td>
<td>Web Development</td>
<td></td>
</tr>
<tr>
<th>Friday</th>
<td></td>
<td>Python</td>
<td>Data Science</td>
<td></td>
</tr>
<tr>
<th>Saturday</th>
<td></td>
<td>Physics</td>
<td>IOT</td>
<td>Web Development</td>
</tr>
</table>
<style>
     th{
              color: black;
              background-color: lightskyblue ;          
         }
         td{
              color: black;
              background-color: darkturquoise;
              
         }
         table{
              border-collapse: collapse;
              color: rgb(0, 0, 0);
              font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
              font-size:medium;
              top: 700px;
         }
    </style>
<table width="1300px" height="300px" border="5px" >
     <tr>
         <th>S.No.</th>
         <th>Subject Code</th>
         <th>Subject Name</th>
     </tr>
     <tr>
         <th>1.</th>
         <td>19AI414</td>
         <td>Fundamentals of Web Application Development (FWAD)</td>
     </tr>
     <tr>
         <th>2.</th>
         <td>19AI403</td>
         <td>Introduction to Data Science</td>
     </tr>
     <tr>
         <th>3.</th>
         <td>19AI301</td>
         <td>Python Progamming</td>
     </tr>
     <tr>
         <th>4.</th>
         <td>SH3214</td>
         <td>Physics for Quantum Computing</td>
     </tr>
     <tr>
         <th>5.</th>
         <td>19CS420</td>
         <td>Prototypes of IoT</td>
     </tr>
     <tr>
         <th>6.</th>
         <td>19EE404</td>
         <td>Digital Electronics</td>
     </tr>
     </div>
 </table>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        img {
            margin: 0;
            padding: 0;
            display: block; /* Prevents inline spacing issues */
        }
    </style>
```
settings.py
```
from pathlib import Path

import os

BASE_DIR = Path(__file__).resolve().parent.parent

SECRET_KEY = 'django-insecure-%ujgd89hdzex=((g_k$f()czaie#_qt^jon6d1xgt9qg#=jcas'

DEBUG = True

ALLOWED_HOSTS = []

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'experiment1',

]

MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
]

ROOT_URLCONF = 'timetable.urls'

TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]

WSGI_APPLICATION = 'timetable.wsgi.application'

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}

AUTH_PASSWORD_VALIDATORS = [
    {
        'NAME': 'django.contrib.auth.password_validation.UserAttributeSimilarityValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.MinimumLengthValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.CommonPasswordValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.NumericPasswordValidator',
    },
]

LANGUAGE_CODE = 'en-us'

TIME_ZONE = 'UTC'

USE_I18N = True

USE_TZ = True

STATIC_URL = 'static/'

DEFAULT_AUTO_FIELD = 'django.db.models.BigAutoField
```
urls.py
```
from django.contrib import admin

from django.urls import path,include

from experiment1 import views

urlpatterns = [
    #path('admin/', admin.site.urls),
    path('slot',views.table)
    ]
```
views.py
```
from django.shortcuts import render

def table(request):

    return render(request,'first.html')
```
# OUTPUT
![alt text](<Screenshot 2024-12-02 111906.png>)
# RESULT
The program for creating slot timetable using basic HTML tags is executed successfully.

# Online Service Provider

Online service provider (OSP) system developed for the course CSE 408: Software Development.\
OSP implements a website built with Django, python, and MySQL where:
* Customers can search for and order services to be delivered to them and give ratings accordingly.

* Service providers can present their services, accept or reject orders from customers, and give ratings to customers accordingly.

* Admins can add new categories and services for the system and approve or reject service providers' requests to join the system.

![](img.png)

Please refer to [manual](Documentation/User_Manual_and_Use_Case.pdf) and [Software requirements and specification](Documentation/Software_Requirements_Specification_ISD.pdf) for details.

## Requirements

1. [Django](https://www.djangoproject.com/) 2.2.4
1. [MySQL](https://dev.mysql.com/downloads/mysql/) server 8.0.32
1. [mysqlclient](https://pypi.org/project/mysqlclient/) 1.4.5

## Setup

Update lines 80-89 of [settings.py](osp/settings.py) in osp folder
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql', 
        'NAME': 'osp',
        'USER': 'root',
        'PASSWORD': 'root',
        'HOST': 'localhost',   # Or an IP Address that your DB is hosted on
        'PORT': '3306',
    }
}
```
Here change NAME, USER, and PASSWORD according to your settings.\
Run:
```
python manage.py makemigrations
python manage.py migrate
```
Finally, run server:
```
python manage.py runserver
```
Note: In browser, entering the server link (e.g., http://127.0.0.1:8000 after the runserver command) will return 404; however, adding /account, /provider, or /admins to the link will work.

## Template

We have used the following website template for this project:\
https://colorlib.com/wp/template/cryptos/

## Map API

To implement location functionalities, we have used [Leaflet](https://leafletjs.com/)
# Django_with_PostgreSQL
How to use PostgreSQL database with Django project

### 1. [Download](https://www.postgresql.org/download/) and install PostgreSQL (With PgAdmin)
### 2. Create Django project
```
> django-admin startproject project_name
```
### 3. Create database
![](https://i.postimg.cc/bN12BvJm/1.png)
![](https://i.postimg.cc/cJLgCMcz/2.png)

### 4. Change code in settings.py
## Before
settings.py
```
DATABASES = {
    'default': {
            'ENGINE': 'django.db.backends.sqlite3',
            'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}
```

## After
settings.py
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': 'db', 
        'USER': 'postgres',
        'PASSWORD': '', // The password for the user you set during the PosgreSQL instalation
        'HOST': '127.0.0.1',
        'POST': '5432', //5432 is default port for PosgreSQl
    }
}
```
### 5. Make migrations
```
> python manage.py makemigrations
```
```
> python manage.py migrate
```
___
## In the end you can check tables there 
Servers -> PosgreSQL -> Databases -> db (name of your database) -> Schemas -> public -> Tables

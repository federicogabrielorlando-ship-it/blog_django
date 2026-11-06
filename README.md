# Blog Django

Proyecto base de un blog web desarrollado con Django.

Preentrega 7 del curso Fundamentos de programación con Python para datos (Coderhouse).
Autor: Federico Orlando.

## Descripción

Este repositorio tiene la estructura inicial de un proyecto Django para construir un blog. Es la continuación del blog por consola de las preentregas anteriores ([blog_consola](https://github.com/federicogabrielorlando-ship-it/blog_consola)), que ahora pasa a ser una aplicación web.

Por ahora incluye:

- El proyecto `blog_project` con su configuración (`settings.py`, `urls.py`, `asgi.py`, `wsgi.py`).
- La aplicación `posts`, registrada en `INSTALLED_APPS`.
- Idioma en español (`es-ar`) y zona horaria de Buenos Aires (`America/Argentina/Buenos_Aires`).
- `requirements.txt` con las dependencias y `.gitignore` para no subir el entorno virtual ni la base de datos local.

Todavía no tiene modelos, vistas ni templates: eso se agrega en las próximas entregas.

## Requisitos

- Python 3.12 o superior (yo lo armé con Python 3.14).
- Git.

## Instalación

Clonar el repositorio:

```bash
git clone https://github.com/federicogabrielorlando-ship-it/blog_django.git
```

Entrar a la carpeta del proyecto:

```bash
cd blog_django
```

Crear el entorno virtual:

```bash
python -m venv venv
```

Activar el entorno virtual:

En Windows PowerShell:

```bash
.\venv\Scripts\Activate.ps1
```

En Windows (símbolo del sistema):

```bash
venv\Scripts\activate
```

En Linux o macOS:

```bash
source venv/bin/activate
```

Instalar las dependencias:

```bash
pip install -r requirements.txt
```

## Ejecutar el servidor

```bash
python manage.py runserver
```

Abrir en el navegador:

```
http://127.0.0.1:8000/
```

Tiene que aparecer la pantalla inicial de Django (en español). Para detener el servidor: `Ctrl + C`.

La primera vez la terminal avisa que hay migraciones sin aplicar. Es normal en esta etapa y no impide que el servidor funcione; se pueden aplicar con `python manage.py migrate`.

## Estructura del proyecto

```
blog_django/
├── manage.py
├── requirements.txt
├── README.md
├── .gitignore
├── blog_project/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
└── posts/
    ├── __init__.py
    ├── admin.py
    ├── apps.py
    ├── migrations/
    │   └── __init__.py
    ├── models.py
    ├── tests.py
    └── views.py
```

## Aplicaciones

- `posts`: aplicación principal del blog, para manejar las publicaciones. Está registrada en `blog_project/settings.py` como `'posts.apps.PostsConfig'`.

## Configuración

En `blog_project/settings.py`:

```python
INSTALLED_APPS = [
    ...
    # Aplicaciones propias
    'posts.apps.PostsConfig',
]

LANGUAGE_CODE = 'es-ar'
TIME_ZONE = 'America/Argentina/Buenos_Aires'
```

## Qué no se sube al repositorio

El `.gitignore` deja afuera el entorno virtual (`venv/`), los archivos temporales de Python (`__pycache__/`, `*.pyc`), las variables privadas (`.env`) y la base de datos local (`db.sqlite3`).

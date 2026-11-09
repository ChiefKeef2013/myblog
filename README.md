# myblog

A small blog built with Django. Users can register, log in, and write their own posts.

## Features

- User registration and authentication (Django auth)
- Create / view blog posts, each linked to its author
- Post list and detail pages
- Django admin for content management
- SQLite database for local development

## Tech stack

| Layer    | Tool            |
| -------- | --------------- |
| Language | Python          |
| Framework| Django          |
| Database | SQLite          |
| Templates| Django templates|
| Styles   | plain CSS       |

## Project structure

```
blog/                  # repository root
├── myblog/            # Django project
│   ├── myblog/        # settings, urls, wsgi/asgi
│   ├── posts/         # main app: models, views, forms, templates, static
│   └── manage.py
├── requirements.txt
└── README.md
```

## Local development

```bash
# 1. Create and activate a virtual environment
python -m venv venv
venv\Scripts\activate        # Windows
# source venv/bin/activate   # macOS / Linux

# 2. Install dependencies
pip install -r requirements.txt

# 3. Apply migrations and create a superuser
cd myblog
python manage.py migrate
python manage.py createsuperuser

# 4. Run the dev server
python manage.py runserver
```

The site is then available at http://127.0.0.1:8000/ and the admin panel at http://127.0.0.1:8000/admin/.

## Deployment notes

This is a server-side Django application, so it cannot be hosted on GitHub Pages
(which only serves static files). To publish it online, use a host that runs Python
web apps — for example Render, Railway, or PythonAnywhere. You will need to set
`DEBUG = False`, define `ALLOWED_HOSTS`, move `SECRET_KEY` to an environment
variable, and serve static files properly.

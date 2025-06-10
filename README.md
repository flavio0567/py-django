# Django REST API: Actors App

This project is a Django REST API for managing actors, built with Django and Django REST Framework.

## Features

- List all actors
- Create a new actor
- Retrieve, update, and delete an actor by ID
- Admin interface for managing actors

## Project Structure

```
djangoRESTAPI_project/
├── actors_app/
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── serializers.py
│   ├── tests.py
│   ├── urls.py
│   ├── views.py
│   └── migrations/
├── djangoRESTAPI_project/
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── db.sqlite3
└── manage.py
```

## Setup Instructions

1. **Clone the repository** and navigate to the project directory.

2. **Create and activate a virtual environment:**
   ```sh
   python -m venv env
   source env/bin/activate  # On Windows: env\Scripts\activate
   ```

3. **Install dependencies:**
   ```sh
   pip install django djangorestframework
   ```

4. **Apply migrations:**
   ```sh
   python manage.py migrate
   ```

5. **Create a superuser (optional, for admin access):**
   ```sh
   python manage.py createsuperuser
   ```

6. **Run the development server:**
   ```sh
   python manage.py runserver
   ```

## API Endpoints

- `GET /actors/` — List all actors
- `POST /actors/` — Create a new actor
- `GET /actors/<id>/` — Retrieve an actor by ID
- `PUT /actors/<id>/` — Update an actor by ID
- `DELETE /actors/<id>/` — Delete an actor by ID

## Example Model

The `Actor` model (see [`actors_app/models.py`](djangoRESTAPI_project/actors_app/models.py)):

```python
class Actor(models.Model):
    name = models.CharField(max_length=100, unique=True, null=True, blank=True)
    age = models.IntegerField()
```

## Admin Interface

Access the Django admin at `http://127.0.0.1:8000/admin/` after creating a superuser.

## Configuration

- Database: SQLite (default)
- Installed apps: `rest_framework`, `actors_app`, and Django defaults (see [`djangoRESTAPI_project/settings.py`](djangoRESTAPI_project/djangoRESTAPI_project/settings.py))

## License

This project is for educational purposes.


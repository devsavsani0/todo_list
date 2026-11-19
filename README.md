# Todo List

A lightweight task manager built with Django. Add tasks, edit their titles, and remove tasks when they are complete. The app stores task data in a local SQLite database and includes a responsive, dark-themed interface.

## Features

- Create and view tasks
- Edit task titles
- Delete tasks with a confirmation step
- SQLite-backed storage

## Requirements

- Python 3.10 or later
- pip

## Setup

1. Clone the repository and move into the project directory.
2. Create and activate a virtual environment:

   **Windows (PowerShell):**

   ```powershell
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```

   **macOS/Linux:**

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Create the database tables:

   ```bash
   python manage.py migrate
   ```

5. Start the development server:

   ```bash
   python manage.py runserver
   ```

6. Open [http://127.0.0.1:8000/](http://127.0.0.1:8000/) in your browser.

## Deploying to Vercel

Vercel detects the Django project from `manage.py` and its WSGI configuration.
Set the `DJANGO_SECRET_KEY` environment variable in Vercel to a unique secret
before deploying. Vercel-provided deployment hostnames are allowed automatically.
If you use a custom domain, add it to `DJANGO_ALLOWED_HOSTS` as a comma-separated
list of hostnames (without `https://`).

The app currently uses SQLite. Vercel's function filesystem is not persistent,
so tasks created after deployment are not reliably retained. Use a persistent
database service before relying on hosted task storage.

## Running tests

Run the Django test suite with:

```bash
python manage.py test
```

## Project structure

- `TodoList/` — Django project settings and URL configuration
- `todo_list/` — task model, views, forms, templates, and tests
- `static/` — application styles
- `db.sqlite3` — local development database, created when migrations are run

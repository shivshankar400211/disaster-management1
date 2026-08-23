# RakshaSetu — Django Full-Stack Prototype

AICTE Smart India Hackathon 2026 · PS 26206 · Disaster Management

This project merges the previous frontend prototype with a Django backend.

## Architecture

Browser
  -> Django URLs
  -> Django Templates / Static UI
  -> Django REST Framework API
  -> Django ORM
  -> SQLite by default (easy development)
  -> PostgreSQL + PostGIS recommended for production

## Modules

- Dashboard / Command Center
- Users and roles
- Disaster incidents
- Emergency alerts
- Rescue teams and assignments
- Shelters
- Hospitals and ambulances
- Relief resources
- Missing persons
- Risk zones
- AI/risk-score placeholder service
- API endpoints
- Django admin

## Run locally

Python 3.11+ recommended.

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Linux/macOS
source venv/bin/activate

pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Open:
- Dashboard: http://127.0.0.1:8000/
- Admin: http://127.0.0.1:8000/admin/
- API root: http://127.0.0.1:8000/api/

## Seed demo data

```bash
python manage.py seed_demo
```

## Production recommendations

- PostgreSQL + PostGIS
- Redis + Celery for background jobs
- Django Channels for WebSockets
- Firebase Cloud Messaging/SMS gateway for alerts
- Object storage for incident photos/videos
- Proper RBAC, audit logs and encryption
- Real external disaster/weather/river data
- A separately deployed ML service or Django-integrated ML pipeline


## Cloud deployment

See `DEPLOY_RENDER.md` for a managed deployment path using Render + PostgreSQL.
The project includes `render.yaml`, `Procfile`, `runtime.txt`, Gunicorn, WhiteNoise,
PostgreSQL support through `DATABASE_URL`, and production environment settings.

# RakshaSetu — Render Deployment

## 1. Create a GitHub repository
Create a new repository and upload the contents of this folder.

## 2. Deploy with Render Blueprint
In Render, choose **New → Blueprint** and select your GitHub repository.
Render will read `render.yaml`, create the Django web service and PostgreSQL database.

## 3. If your generated URL is not `rakshasetu.onrender.com`
After the first deployment, update these environment variables in the Render web service:
- `ALLOWED_HOSTS`
- `CSRF_TRUSTED_ORIGINS`
- `CORS_ALLOWED_ORIGINS`

Example:
- ALLOWED_HOSTS: `rakshasetu-abc123.onrender.com`
- CSRF_TRUSTED_ORIGINS: `https://rakshasetu-abc123.onrender.com`
- CORS_ALLOWED_ORIGINS: `https://rakshasetu-abc123.onrender.com`

Then redeploy.

## 4. Create an admin account
The deployment automatically runs migrations. To create a superuser, open a Render Shell for the web service and run:

```bash
python manage.py createsuperuser
```

## 5. Optional demo data
From Render Shell:

```bash
python manage.py seed_demo
```

## 6. Public URLs
Once deployed:

```text
https://YOUR-SERVICE.onrender.com/
https://YOUR-SERVICE.onrender.com/api/
https://YOUR-SERVICE.onrender.com/admin/
```

## Important
Do not use `python manage.py runserver` as the production server.
The project uses Gunicorn + WhiteNoise + PostgreSQL environment configuration.

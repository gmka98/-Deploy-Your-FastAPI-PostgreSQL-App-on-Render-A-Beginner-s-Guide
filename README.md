# -Deploy-Your-FastAPI-PostgreSQL-App-on-Render-A-Beginner-s-Guide
A beginner-friendly guide to deploying a FastAPI app with a PostgreSQL database on Render. Includes step-by-step instructions, example code, and tips for production-ready deployment.

---

## 📦 Tech Stack

- **FastAPI** – Modern, fast Python web framework
- **PostgreSQL** – Render-managed SQL database
- **Uvicorn** – ASGI server
- **SQLAlchemy** – ORM for database modeling
- **Render.com** – For hosting the app and DB

---

## 🚀 Deploy to Render (Step-by-Step)

### 1. Push to GitHub

Ensure your project is hosted on a public or private GitHub repository.

### 2. Create `render.yaml`

This defines your deployment settings:

```yaml
services:
  - type: web
    name: fastapi-app
    env: python
    plan: free
    buildCommand: "pip install -r requirements.txt"
    startCommand: "uvicorn fastapi_app.main:app --host 0.0.0.0 --port 10000"
    envVars:
      - key: DATABASE_URL
        value: your_render_database_url


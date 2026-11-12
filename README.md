# Student Task Management System

A Flask-based academic task manager with user registration, login, task creation, deadlines, priorities, completion tracking and a dashboard.

## Run locally with Docker

1. Install Docker Desktop and start it.
2. Open a terminal in this project folder.
3. Build and start the application:

   ```bash
   docker compose up --build -d
   ```

4. Open http://localhost:5008
5. Stop the container:

   ```bash
   docker compose down
   ```

The named Docker volume `task_data` stores the SQLite database across container restarts. To remove the database too, run `docker compose down -v`.

## Deploy online with Render

1. Create a GitHub repository and upload all project files.
2. Sign in to Render and choose **New + → Blueprint**.
3. Connect the GitHub repository containing `render.yaml`.
4. Review and create the service.
5. Wait for deployment, then open the public `onrender.com` URL.
6. Test registration, login and task creation.

**Important:** Render persistent disks may require a paid plan. The included `render.yaml` requests a 1 GB disk so SQLite data persists. Check the current Render pricing and disk availability before deploying. If using a free service without persistent storage, local SQLite data can be lost when the service restarts or redeploys.

## Useful Docker commands

```bash
# See running containers
docker ps

# View application logs
docker compose logs -f

# Rebuild after changing code
docker compose up --build -d

# Stop the application
docker compose down
```

## Main routes

- `/` — Home page
- `/register` — Create an account
- `/login` — Sign in
- `/dashboard` — Manage tasks (login required)
- `/health` — Deployment health check

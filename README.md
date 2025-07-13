# 🐳 Dockerized Django Notes App

ALHAMDULILLAH 🙌 — Built a fully Dockerized, production-style **Notes App** using Django, MySQL, and Nginx.  
Inspired by [Train With Shubham](https://www.youtube.com/@TrainWithShubham)'s amazing content 💻🔥

---

## 🚀 Tech Stack

- **Python** + **Django** – Backend logic  
- **MySQL** – Database  
- **Gunicorn** – WSGI server for Django  
- **Nginx** – Reverse proxy to serve the app  
- **Docker Compose** – Container orchestration

---

## 📁 Project Structure

```
.
├── app/                 # Django app (models, views)
├── notesapp/            # Django project (settings, wsgi)
├── nginx/
│   └── default.conf     # Nginx config
├── Dockerfile           # Django build config
├── docker-compose.yml   # Main Docker Compose config
├── .env                 # Environment variables (not pushed)
├── mysql-data/          # MySQL volume (ignored)
├── requirements.txt     # Python dependencies
└── manage.py            # Django CLI entrypoint
```

---

## ⚙️ Getting Started

### 🔧 Prerequisites

- Docker & Docker Compose installed  
- Basic knowledge of Django (helpful)

---

### 🧪 1. Clone the Repository

```bash
git clone https://github.com/your-username/django-notes-app.git
cd django-notes-app
```

---

### 🔐 2. Create a `.env` File

In the root folder, create a `.env` file:

```env
DB_NAME=test_db
DB_USER=root
DB_PASSWORD=root
DB_HOST=db
SECRET_KEY=your_django_secret_key
DEBUG=1
```

---

### 🐳 3. Run the App with Docker

```bash
docker-compose up --build
```

This will:
- Run MySQL on port 3306  
- Run Django with Gunicorn on port 8000  
- Expose the app via Nginx on port 80  
- Auto-migrate database on start

---

### 🌐 Access the App

| Feature        | URL                      |
|----------------|---------------------------|
| Main App       | http://localhost          |
| Django Admin   | http://localhost/admin    |

Use the `createsuperuser` command to create a login for admin.

---

## 🩺 Healthchecks Included

- ✅ **MySQL** ping check  
- ✅ **Django** `/admin` endpoint check via curl  
- ✅ All services restart automatically if failed  

---

## 📦 Persistent Volumes

MySQL data is stored in `./mysql-data`, so data won’t be lost when containers restart.

> NOTE: This folder is ignored in Git using `.gitignore`

---

## 📜 Useful Commands

Stop containers:
```bash
docker-compose down
```

Rebuild all:
```bash
docker-compose up --build
```

Check running containers:
```bash
docker ps
```

---

## 📸 Screenshots (Optional)

*Add screenshot of your app and admin panel here.*

---

## 🤝 Credits

Inspired by:  
🎥 [Train With Shubham](https://www.youtube.com/@TrainWithShubham)  
💻 Repo Reference: [LondheShubham153/django-notes-app](https://github.com/LondheShubham153/django-notes-app)

---

## 🪪 License

This project is licensed under the MIT License.

---

## 🙋‍♂️ Want to Contribute?

Feel free to fork and PR — or drop a ⭐ if you liked it 😄

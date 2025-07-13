# Secure Vault

A secure, full-stack file management system featuring a Django REST API backend and a modern React frontend. The application allows users to upload, list, download, and delete files with robust security and cloud storage support.

---

## 🚀 Technology Stack

**Backend:**
- Python 3.9+
- Django 4.x
- Django REST Framework
- SQLite (development)
- AWS S3 (file storage)
- Docker

**Frontend:**
- React (TypeScript)
- Tailwind CSS
- React Query
- Axios
- Docker

---

## 📦 Features

- Upload files (up to 10MB)
- List, search, and paginate files
- Download and delete files
- Responsive, modern UI
- Secure file storage (UUID-based, S3 support)
- API integration with authentication and CORS

---

## 🛠️ Getting Started

### Prerequisites

- Python 3.9+ and pip (for backend)
- Node.js v18+ and npm (for frontend)
- Docker (optional, for containerized setup)
- AWS account & S3 bucket (for production file storage)

---

### Backend Setup

1. **Create and activate a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure environment:**
   - Create a `.env` file in `backend/` with Django and AWS settings.

4. **Run migrations and create superuser:**
   ```bash
   python manage.py migrate
   python manage.py createsuperuser
   ```

5. **Start the server:**
   ```bash
   python manage.py runserver
   ```
   - API available at `http://localhost:8000/api`

**Docker:**
```bash
docker build -t file-hub-backend .
docker run -p 8000:8000 file-hub-backend
```

---

### Frontend Setup

1. **Install dependencies:**
   ```bash
   cd frontend
   npm install
   ```

2. **Start the development server:**
   ```bash
   npm start
   ```
   - App runs at `http://localhost:3000`

**Docker:**
```bash
docker build -t file-hub-frontend .
docker run -p 3000:3000 file-hub-frontend
```

**Configuration:**
- Set the API endpoint via `REACT_APP_API_URL` (defaults to `http://localhost:8000/api`).

---

## 🔗 API Overview

- `GET /api/files/` — List files (supports search, sort, pagination)
- `POST /api/files/` — Upload file (multipart form)
- `GET /api/files/<uuid>/` — File details
- `DELETE /api/files/<uuid>/` — Delete file

---

## 🔒 Security

- UUID-based file identification
- WhiteNoise for static file serving
- CORS configuration for frontend integration
- AWS S3 access control (IAM, bucket policies)
- Django security features: CSRF, XSS, SQL injection protection

---

## 📁 Project Structure

```
secure-file-hub/
  backend/    # Django backend (API, models, storage)
  frontend/   # React frontend (UI, API integration)
  docker-compose.yml
```


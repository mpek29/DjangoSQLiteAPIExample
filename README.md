# DjangoSQLiteAPIExample

## 🚀 Overview
![Main Preview](assets/img/main.png)

This project is a minimalist example of a Django API that allows access to an SQLite database. The API offers two access modes:
- 📂 **Unauthenticated Access**: Some parts of the database are accessible without authentication.
- 🔑 **Authenticated Access via Token**: Some data requires authentication using a token.

## 🎯 Features
- 🔄 **REST API**: Communication via RESTful endpoints.
- 🔓 **Public Access**: Some data is accessible without authentication.
- 🔐 **Secure Access**: Restricted data access via token authentication.
- 📁 **SQLite Database**: Simple and efficient for data storage.

## 📋 Prerequisites
- **Python**: Version 3.8 or higher
- **Django**: Version 4.x
- **Django REST Framework**: For API management

## 🚀 Installation and Setup

### 🛠️ Installation
1. **Clone the repository**:
   ```bash
   git clone https://github.com/mpek29/DjangoSQLiteAPIExample.git
   cd .\DjangoSQLiteAPIExample\
   ```

2. **Create a virtual environment**:
   ```bash
   python -m venv env
   source env/bin/activate  # On Windows: env\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Apply migrations**:
   ```bash
   python manage.py migrate
   ```

5. **Start the server**:
   ```bash
   python manage.py runserver
   ```

## 📡 Using the API

### 📂 Unauthenticated Access
Some routes are accessible without authentication:
```bash
curl http://127.0.0.1:8000/api/public/
```

### 🔑 Authenticated Access via Token
1. **Obtain an authentication token**:
   ```bash
   curl -X POST http://127.0.0.1:8000/api/token/ -d "username=user&password=pass"
   ```

   This will return a token in the following format:
   ```json
   { "token": "abc123xyz456" }
   ```

2. **Use the token to access protected routes**:
   ```bash
   curl -H "Authorization: Token abc123xyz456" http://127.0.0.1:8000/api/protected/
   ```

## 📂 Project Structure
```
├── django_sqlite_api/
│   ├── settings.py  # Django Configuration
│   ├── urls.py  # API Routes
│   ├── views.py  # REST Views
│   ├── models.py  # Database Models
│   ├── serializers.py  # Data Serialization
├── db.sqlite3  # SQLite Database
├── manage.py  # Django Management Command
└── requirements.txt  # Dependencies
```

## 🌟 License
Open-source project, free to use and modify! 🎉

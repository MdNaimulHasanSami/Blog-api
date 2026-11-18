# Blog API - Django REST Framework

A simple and robust RESTful API for managing blog posts, built with **Django**, **Django REST Framework (DRF)**, and documented using **drf-spectacular** (Swagger UI & ReDoc).

## Features

- **CRUD Operations:** Create, Read, Update (Partial), and Delete blog posts.
- **UUID Primary Keys:** Uses UUID4 for secure and unique blog identifiers.
- **API Documentation:** Interactive API documentation powered by Swagger UI and ReDoc.
- **JSON Responses:** Clean and structured JSON responses with appropriate HTTP status codes.

## Tech Stack

- **Backend:** Python, Django
- **API Framework:** Django REST Framework (DRF)
- **Documentation:** drf-spectacular (OpenAPI 3.0)
- **Database:** SQLite (Default)

## Project Structure

```text
Bloger-main/
├── blog/
│   ├── migrations/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── serializers.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── src/
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── manage.py
├── requirements.txt
└── README.md
```

## Installation & Setup

Follow these steps to set up and run the project locally:

### 1. Clone the Repository
```bash
git clone <your-repository-url>
cd Bloger-main
```

### 2. Create and Activate a Virtual Environment
```bash
# Create virtual environment
python -m venv venv

# Activate on Windows
venv\Scripts\activate

# Activate on macOS/Linux
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Apply Database Migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### 5. Create a Superuser (Optional)
To access the Django Admin panel:
```bash
python manage.py createsuperuser
```

### 6. Run the Development Server
```bash
python manage.py runserver
```
The API will be available at `http://127.0.0.1:8000/`.

---

## API Endpoints

| HTTP Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/` | Retrieve a list of all blogs |
| `POST` | `/blogs/create/` | Create a new blog post |
| `GET` | `/blogs/<uuid:pk>/` | Retrieve details of a specific blog |
| `PATCH` | `/blogs/<uuid:pk>/update/` | Partially update a specific blog |
| `DELETE` | `/blogs/<uuid:pk>/delete/` | Delete a specific blog |

### Example Request Payload (`POST /blogs/create/`)
```json
{
  "title": "Getting Started with Django REST Framework",
  "description": "This is a comprehensive guide on building REST APIs using DRF."
}
```

---

## API Documentation

Once the server is running, you can explore and test the API using the built-in interactive documentation:

- **Swagger UI:** [http://127.0.0.1:8000/blogs/docs/](http://127.0.0.1:8000/blogs/docs/)
- **ReDoc:** [http://127.0.0.1:8000/blogs/redoc/](http://127.0.0.1:8000/blogs/redoc/)
- **OpenAPI Schema:** [http://127.0.0.1:8000/blogs/schema/](http://127.0.0.1:8000/blogs/schema/)

## License

This project is open-source and available under the [MIT License](LICENSE).
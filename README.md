# ALX Travel App

ALX Travel App is a Django-based web application designed for managing hotel listings and bookings. It provides a robust RESTful API backend, complete with automated API documentation, secure configuration management, and a setup for future asynchronous task handling.

## Key Highlights

-   **RESTful API**: Built with Django REST Framework to expose application data and functionality.
-   **Database**: Uses MySQL as the primary database, configured securely using environment variables.
-   **API Documentation**: Automatic API documentation powered by `drf-yasg` to generate Swagger/OpenAPI schemas.
-   **Secure Configuration**: Manages sensitive information like secret keys and database credentials using `django-environ` and `.env` files.
-   **CORS Support**: `django-cors-headers` is configured to handle Cross-Origin Resource Sharing.
-   **Asynchronous Tasks**: Prepared for future integration with Celery and RabbitMQ for handling background processes.

## Technology Stack

-   **Backend**: Python, Django, Django REST Framework
-   **Database**: MySQL
-   **API Documentation**: `drf-yasg` (Swagger/OpenAPI)
-   **Async Tasks**: Celery, RabbitMQ (or other message broker)
-   **Environment Management**: `django-environ`

---

## Getting Started

Follow these instructions to get a local copy of the project up and running for development and testing purposes.

### Prerequisites

-   Python 3.8+
-   Git
-   A running MySQL Server instance.
-   `pip` and `venv` for package management.

### 1. Clone the Repository

First, clone the project repository from GitHub:

```bash
git clone https://github.com/alx_travel_app.git
cd alx_travel_app
```

### 2. Set Up a Virtual Environment

It is highly recommended to use a virtual environment to manage project dependencies.

```bash
# Create a virtual environment
python3 -m venv venv

# Activate the virtual environment
# On macOS/Linux:
source venv/bin/activate
# On Windows:
# .\venv\Scripts\activate
```

### 3. Install Dependencies

Install all the required Python packages from the `requirements.txt` file.

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

The project uses a `.env` file to store sensitive configuration. Create a `.env` file in the project root by copying the example structure below.

```bash
touch .env
```

Now, add the following configuration to your `.env` file and replace the placeholder values with your actual database credentials.

```ini
# .env

# Django Settings
SECRET_KEY='your-strong-and-unique-secret-key'
DEBUG=True

# Database Settings (MySQL)
DATABASE_NAME='alxtravel_db'
DATABASE_USER='your_db_user'
DATABASE_PASSWORD='your_db_password'
DATABASE_HOST='127.0.0.1' # or your DB host
DATABASE_PORT='3306'
```

**Important:** The `.env` file is included in `.gitignore` and should **never** be committed to version control.

### 5. Set Up the Database

Ensure your MySQL server is running. You will need to create the database that you specified in your `.env` file.

You can do this via the MySQL command line:

```sql
CREATE DATABASE alxtravel_db;
```

### 6. Run Database Migrations

Apply the initial database migrations to set up the necessary tables.

```bash
python manage.py migrate
```

### 7. Run the Development Server

You are now ready to start the Django development server.

```bash
python manage.py runserver
```

The application will be available at `http://127.0.0.1:8000/`.

---

## API Documentation

This project includes automatically generated API documentation using Swagger. Once the server is running, you can access the documentation at the following endpoints:

-   **Swagger UI**: [http://127.0.0.1:8000/swagger/](http://127.0.0.1:8000/swagger/)
-   **ReDoc**: [http://127.0.0.1:8000/redoc/](http://127.0.0.1:8000/redoc/)

## Project Structure

```
alx_travel_app/
├── alx_travel_app/       # Django project configuration
│   ├── settings.py
│   ├── urls.py
│   └── ...
├── listings/             # Core application for listings logic
│   ├── models.py
│   ├── views.py
│   └── ...
├── .env                  # (Local) Environment variables (ignored by Git)
├── .gitignore            # Files and directories to be ignored by Git
├── manage.py             # Django's command-line utility
└── requirements.txt      # Project dependencies
```
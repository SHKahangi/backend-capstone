# Description
This is the final project for the Capstone Course of the Back-End Development course of Meta. This project showcases the culmination of skills developed over the course.

# Project Structure
The project consists of three main components: `client`, `server`, and `config`. The `client` app manages the frontend interactions, the `server` app handles backend operations, and the `config` directory contains global settings.

# Installation

Install the required packages:

```bash
pipenv install
```

Activate the virtual environment:

```bash
pipenv shell
```

# Setup
Configure the database settings in your Django settings:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'capstone_db',
        'USER': 'capstone_user',
        'PASSWORD': 'secure_password',
        'HOST': 'localhost',
        'PORT': '',
    },
}
```
💡 Adjust these settings based on your local or production environment.

Apply database migrations:

```bash
python manage.py migrate
```

# Environment Variables
Set up environment variables to manage sensitive data:

Create a `.env` file in the server directory:

```plaintext
DB_USER=your_db_user
DB_PASS=your_db_password
SECRET_KEY=your_secret_key
```

💡 Ensure `django-environ` is used to load these variables, which can be installed via `pipenv install`.

# API Endpoints
The `server` app provides several endpoints, alongside user management provided by the `djoser` package.

Include a bearer token for secured endpoints:

```bash
{'Authorization': 'Bearer <token>'}
```

### Server Endpoints

- **/api/products/**
  - GET: Fetch all products
  - POST: Add a new product

- **/api/products/{productId}**
  - GET: Fetch a specific product
  - PUT: Update a product
  - DELETE: Remove a product

### Djoser Authentication Endpoints

Refer to the [Djoser documentation](https://djoser.readthedocs.io/en/latest/getting_started.html#available-endpoints) for detailed usage of user-related endpoints.

# Testing
Ensure all components function correctly with unit tests.

Run tests:

```bash
python manage.py test
```

Expected output:

```plaintext
Found 20 test(s).
Creating test database for alias 'default'...
System check identified no issues (0 silenced).
....................
----------------------------------------------------------------------
Ran 20 tests in 5.000s

OK
Destroying test database for alias 'default'...
```

💡 The tests cover both API functionality and the database integration through Django ORM.

This structured outline should help you organize your project documentation efficiently, offering clarity on installation, setup, API usage, and testing procedures.
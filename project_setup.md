# Chapter Project Setup Guide

This guide provides detailed instructions for setting up the Chapter library management system project.

## Prerequisites

- Python 3.8 or higher
- pip (Python package installer)
- Git
- Virtual environment tool (venv)

## Step-by-Step Setup

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/Chapter.git
cd Chapter
```

### 2. Set Up Virtual Environment

```bash
# Create virtual environment
python3 -m venv venv

# Activate virtual environment
# On macOS/Linux:
source venv/bin/activate
# On Windows:
# venv\Scripts\activate
```

### 3. Install Dependencies

```bash
# Upgrade pip
pip install --upgrade pip

# Install requirements
pip install -r requirements.txt
```

### 4. Database Setup

#### Using SQLite (Default)

1. Run migrations:
```bash
python3 manage.py makemigrations
python3 manage.py migrate
```

2. Load initial data:
```bash
python3 manage.py loaddata initial_data.json
```

#### Using MySQL (Optional)

1. Install MySQL server and client
2. Create a new database:
```sql
CREATE DATABASE chapter_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

3. Update settings.py with MySQL configuration:
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'chapter_db',
        'USER': 'your_username',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

4. Run migrations:
```bash
python3 manage.py makemigrations
python3 manage.py migrate
```

### 5. Create Superuser

```bash
python3 manage.py createsuperuser
```

Follow the prompts to create an admin user.

### 6. Run Development Server

```bash
python3 manage.py runserver
```

Access the application at:
- Main site: http://127.0.0.1:8000/
- Admin interface: http://127.0.0.1:8000/admin/

## Project Structure

```
Chapter/
├── Chapter/                 # Main project directory
├── books/                  # Books app
├── authors/               # Authors app
├── rentals/              # Rentals app
├── users/               # Users app
├── publishers/         # Publishers app
├── categories/        # Categories app
├── templates/        # HTML templates
├── static/          # Static files
├── media/          # User-uploaded files
├── manage.py      # Django management script
└── requirements.txt  # Project dependencies
```

## Common Issues and Solutions

### 1. Database Connection Issues

If you encounter database connection issues:
- Verify database credentials in settings.py
- Ensure database server is running
- Check database user permissions

### 2. Static Files Not Loading

If static files are not loading:
```bash
python3 manage.py collectstatic
```

### 3. Migration Issues

If you encounter migration issues:
```bash
# Remove all migrations
rm */migrations/0*.py

# Recreate migrations
python3 manage.py makemigrations
python3 manage.py migrate
```

### 4. Virtual Environment Issues

If you have issues with the virtual environment:
```bash
# Deactivate current environment
deactivate

# Remove old environment
rm -rf venv

# Create new environment
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

## Development Guidelines

1. Always work in a virtual environment
2. Keep requirements.txt updated:
```bash
pip freeze > requirements.txt
```

3. Follow PEP 8 style guide
4. Write tests for new features
5. Document code changes

## Deployment

For production deployment:
1. Set DEBUG = False in settings.py
2. Configure proper database settings
3. Set up static file serving
4. Configure security settings
5. Use a production-grade server (e.g., Gunicorn)
6. Set up proper web server (e.g., Nginx)

## Support

For any issues or questions:
1. Check the documentation
2. Search existing issues
3. Create a new issue if needed

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

This project is licensed under the MIT License. 
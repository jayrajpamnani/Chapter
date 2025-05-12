**This project was completed for the course CS-GY 6083 Principles of Database Systems at New York University by Puneeth Kotha, Jayraj Pamnani, and Ilka Jean.**

# Chapter - Library Management System

A comprehensive library management system built with Django, featuring book management, user management, and rental tracking capabilities.

## Features

- Book Management
  - Add, edit, and delete books
  - Track book details (title, author, ISBN, etc.)
  - Manage book categories and publishers

- Author Management
  - Maintain author profiles
  - Track author details and their books

- User Management
  - User registration and authentication
  - User profile management

- Rental System
  - Track book rentals
  - Manage rental history
  - Handle returns and due dates

- Publisher Management
  - Maintain publisher information
  - Track publisher's book catalog

- Category Management
  - Organize books by categories
  - Easy book categorization

- Study Room Reservations
  - Reserve and manage study rooms

- Event Management
  - Organize and register for seminars and events

- Admin Features
  - Dashboard and analytics

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/Chapter.git
cd Chapter
```

2. Create and activate a virtual environment:
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Set up the database:
```bash
python3 manage.py makemigrations
python3 manage.py migrate
```

5. Create a superuser:
```bash
python3 manage.py createsuperuser
```

6. Run the development server:
```bash
python3 manage.py runserver
```

7. Access the application:
- Main site: http://127.0.0.1:8000/
- Admin interface: http://127.0.0.1:8000/admin/

## Database Setup

The project includes SQL files for initial data population:

1. Run the migrations:
```bash
python3 manage.py migrate
```

2. Load the initial data:
```bash
python3 manage.py loaddata initial_data.json
```

## Contributing

1. Fork the repository
2. Create a new branch
3. Make your changes
4. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contact

For any questions or concerns, please open an issue in the repository.

---



Little Lemon - Django REST API Project
======================================

About the Project
-----------------
Little Lemon is a fictional restaurant, and this project is a back-end web application built using Django and Django REST Framework.

The application provides a RESTful API for managing restaurant menu items and handling table bookings. It also includes user registration and authentication using JWT tokens.

The API is connected to a MySQL database and supports CRUD operations through HTTP methods like GET, POST, PUT, and DELETE.

In addition to the API, the project serves a static HTML homepage and includes unit tests to verify functionality.

This project demonstrates core back-end development skills, including building APIs, connecting to a relational database, implementing authentication, and testing endpoints.

Technologies Used
-----------------
- Django 4.x
- Django REST Framework
- MySQL
- JWT Authentication (via djangorestframework-simplejwt)
- HTML Templates

How to Run the Project
----------------------
1. Clone the repository:
   git clone <your-repo-url>
   cd littlelemon

2. Create a virtual environment:
   python -m venv env
   source env/bin/activate   (Linux/Mac)
   .\env\Scripts\activate    (Windows)

3. Install dependencies:
   pip install -r requirements.txt

4. Set up your MySQL database and configure it in `littlelemon/settings.py`:
   DATABASES = {
       'default': {
           'ENGINE': 'django.db.backends.mysql',
           'NAME': 'littlelemon',
           'USER': 'root',
           'PASSWORD': 'yourpassword',
           'HOST': 'localhost',
           'PORT': '3306',
       }
   }

5. Run migrations:
   python manage.py makemigrations
   python manage.py migrate

6. Start the server:
   python manage.py runserver

Authentication
--------------
This project uses JWT for authentication.

To register a user:
  - POST to `/api/registration/`

To authenticate (token required for bookings/menu POST):
  - Use JWT tokens in the header:
    Authorization: Bearer <access_token>

API Endpoints to Test
---------------------
- `GET /api/menu/` – List menu items
- `POST /api/menu/` – Add a menu item (auth required)
- `GET /api/bookings/` – List bookings (auth required)
- `POST /api/bookings/` – Create a booking (auth required)
- `POST /api/registration/` – Register a new user

Static HTML Page
----------------
- Home page available at `/`, renders `templates/home.html`

Unit Tests
----------
To run tests:
  python manage.py test

Contact
-------
For questions or issues, please raise a GitHub issue in the repository.

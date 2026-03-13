# ACW Blog – Django Social Blogging Platform

ACW Blog is a **social blogging web application built with Django** that allows users to create blogs, interact with other authors, comment on posts, rate blogs, and follow other users.

This project demonstrates **backend web development using Django**, including database relationships, authentication logic, session management, file uploads, and user interaction features.

---

## Features

### User Features

* User registration with profile image
* Secure login with hashed passwords
* Change password functionality
* Password reset via email token
* Profile page with followers and ratings

### Blogging Features

* Create blog posts with images
* View blogs from other users
* Comment on blog posts
* Rate blogs
* View personal blog posts

### Social Features

* Follow other users
* Unfollow users
* View follower count
* View following count

### Admin Features

* Admin dashboard
* View all blogs and comments
* Manage users
* Activate / deactivate user accounts

---

## Tech Stack

**Backend**

* Python
* Django

**Frontend**

* HTML
* CSS
* Django Templates

**Database**

* SQLite

**Other Tools**

* Gmail SMTP (for password reset emails)
* File upload handling

---

## Project Structure

```
ACW-BLOG-Django
│
├── blog/                     # Django project configuration
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
├── handleBlog/               # Main Django application
│   ├── images/               # Uploaded images
│   ├── migrations/
│   ├── templates/            # HTML templates
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── handleEmail.py        # Email utility for password reset
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
│
├── db.sqlite3
├── manage.py
└── README.md
```

---

## Database Models

### CustomUser

Stores user information.

Fields:

* Username
* Email
* Password (hashed)
* Phone number
* About section
* Profile image
* Active / inactive status

---

### Blog

Stores blog posts created by users.

Fields:

* Blog title
* Blog content
* Blog image
* Blog date
* Author (ForeignKey to user)

---

### Comment

Stores comments made on blog posts.

Fields:

* Comment content
* Commenter name
* Comment date
* Associated blog
* Associated user

---

### Rating

Allows users to rate blog posts.

Fields:

* Rating value
* Associated blog
* Associated user

---

### UserProfile

Handles the followers system.

Fields:

* User
* Followers (ManyToMany relationship)

---

## Installation Guide

### 1. Clone Repository

```
git clone https://github.com/Akshit017/ACW-BLOG-Django.git
cd ACW-BLOG-Django
```

---

### 2. Create Virtual Environment

```
python -m venv venv
```

Activate environment

Windows

```
venv\Scripts\activate
```

Mac / Linux

```
source venv/bin/activate
```

---

### 3. Install Dependencies

```
pip install django python-dotenv
```

---

### 4. Run Migrations

```
python manage.py migrate
```

---

### 5. Start Development Server

```
python manage.py runserver
```

Open in browser

```
http://127.0.0.1:8000/
```

---

## Email Configuration

The project uses **Gmail SMTP** for password reset functionality.

Create a `.env` file and add:

```
SECRET_KEY=your_secret_key
EMAIL_HOST_USER=your_email@gmail.com
EMAIL_HOST_PASSWORD=your_app_password
```

---

## Future Improvements

* Add blog search functionality
* Add pagination
* Add blog categories
* Use Django authentication system
* Add like system for blogs
* Deploy project to cloud (Render / AWS)

---

## Author

**Akshit Chauhan**

GitHub
https://github.com/Akshit017

---

## License

This project is built for educational and portfolio purposes.

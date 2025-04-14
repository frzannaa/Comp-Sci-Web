# Comp-Science Website

A full-stack web application developed during my internship at Universitas Sains Malaysia (USM). This project aims to scrape and display detailed information of 41 USM lecturers from Scopus, organizing the data for easier internal access and visualization. The project includes a backend built with Django and a frontend built with HTML, CSS, Bootstrap.

## Table of Contents

- [Tech Stack](#-tech-stack)
- [Installation](#-installation)
- [Project Structure](#-project-structure)
- [Features](#-features)
- [How It Works](#-how-it-works)
- [Usage](#-usage)
- [Notes](#-notes)

---

## Depedencies

This project utilize following frameworks and uses:

- **Python**
- **Django**
- **SQLite** (default database)
- **Requests** (for scraping)
- **HTML, CSS** 


---

## Installation

1. Clone this repository

2. Create and activate a virtual environment
```
python -m venv venv source venv/bin/activate
On Windows: venv\Scripts\activate
```
3. Install dependencies
```
pip install -r requirements.txt
```
4. Run Migrations
```
python manage.py migrate
```
5. Start the development server:
```
python manage.py runserver
```

## Project Structure
```
CS/
├── dosen/
│   ├── migrations/
│   ├── templates/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── scraper.py
│   ├── urls.py
│   └── views.py
├── csproject/
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── db.sqlite3
├── manage.py
└── requirements.txt
```
</details>

## Features
- Scrapes lecturer profiles and publication data from Scopus
- Displays structured data like publication counts and affiliations
- Admin panel for managing lecturer info
- Web portal to view and organize publication details

## How It Works
- The scraper.py script sends HTTP requests to Scopus profiles.
- It extracts and processes data like names, affiliations, and publications.
- Data is saved into Django models (SQLite).
- Views and templates display the data in a clean, Bootstrap-based layout.
- Admin panel is provided by Django for CRUD operations.

## Usage
- Run the server and open http://127.0.0.1:8000/.
- Browse the homepage to view the list of lecturers.
- Click on a name to see more detailed publication info.
- Visit /admin to log in and edit/add data as needed.

## Notes
```
- Scopus page structures may change over time. This scraper is based on the current structure as of the internship period.
- This app was built for internal university use and deployed locally.
- Developed entirely by me during my internship at USM as a solo project.
```

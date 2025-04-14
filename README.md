# Comp-Science Website

A web application developed during my internship at Universitas Sains Malaysia (USM). This project aims to scrape and display detailed information of 41 USM lecturers from Scopus, organizing the data for easier internal access and visualization. The project includes a backend built with Django and a frontend built with HTML, CSS, Bootstrap.

## Table of Contents

- [Depedencies](#-depedencies)
- [Installation](#-installation)
- [Project Structure](#-project-structure)
- [Features](#-features)
- [How It Works](#-how-it-works)
- [Usage](#-usage)
- [API Documentation](#-api-documentation)
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
CS/my-django-project/
├── accounts/              
│   ├── templates/          
│   ├── migrations/         
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── urls.py
│   └── views.py
├── myapp/                  
│   ├── management/commands 
│   ├── static/             
│   ├── templates/         
│   ├── scrapedata.py     
│   ├── models.py
│   ├── views.py
│   └── urls.py
├── myproject/              
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── media/                  
├── db.sqlite3              
├── manage.py               
├── requirements.txt        
└── vercel.json             
```

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

## API Documentation

### 1. Overview

This project scrapes data about lecturers and their publications using an external API (such as the Scopus API). The data is stored in CSV files and served through Django views.

### 2. Scopus Data Scraping

- Endpoint: `http://api.elsevier.com/content/search/scopus`
- The data is retrieved from the Scopus API using a GET request with specific parameters. 

#### Scraping Process

- API Key: Required for authentication (`<your-api-key>`).
- Query Format: Each lecturer’s data is queried by their unique ID.
- Pagination: Data is retrieved in pages using `num_results_per_request` and `offset`.
- Output: The scraped data is saved into CSV files located in the `static` directory, named after the lecturer's ID.

### 3. CSV File Format

Each CSV file contains the following columns:

- Title (string): Title of the paper.
- Authors (string): List of authors (can be multiple authors).
- Publication Date (string): The publication date of the paper.
- DOI (string): Digital Object Identifier of the paper.
- Source Title (string): The name of the journal/conference where the paper was published.

## Notes
```
- Scopus page structures may change over time. This scraper is based on the current structure as of the internship period.
- This app was built for internal university use and deployed locally.
- Developed entirely by me during my internship at USM as a solo project.
```

# Conference Info Platform

> Full-stack web application for managing academic conference information — built with **PHP**, a **MySQL** database, and a **REST API** for programmatic access. Coursework project demonstrating end-to-end web-stack engineering.

[![Status](https://img.shields.io/badge/status-completed-success)]()
[![Stack](https://img.shields.io/badge/stack-PHP%20%2B%20MySQL-777bb4)]()
[![API](https://img.shields.io/badge/REST%20API-yes-green)]()
[![License](https://img.shields.io/badge/license-MIT-lightgrey)]()

---

## TL;DR

| | |
|---|---|
| **Brief** | Build a complete conference-management web platform: CRUD on conferences, programmatic access via REST. |
| **Stack** | PHP backend · MySQL database · HTML/CSS/JS frontend · REST API. |
| **Demonstrates** | Server-side scripting · relational data modelling · API design · full-stack integration. |

---

## What's in the platform

| Feature | What it does |
|---|---|
| Conference listing | Browse upcoming and past conferences with filters by topic and date. |
| Conference detail page | Full information for each conference — agenda, speakers, venue. |
| Admin CRUD | Create / update / delete conferences and associated metadata. |
| REST API | Endpoints for programmatic listing, retrieval, and search of conferences. |
| Authentication | Session-based login for admin actions. |

---

## REST API endpoints

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/conferences` | List all conferences. Supports `?topic=` and `?year=` filters. |
| `GET` | `/api/conferences/{id}` | Retrieve a single conference by ID. |
| `POST` | `/api/conferences` | Create a new conference (auth required). |
| `PUT` | `/api/conferences/{id}` | Update an existing conference (auth required). |
| `DELETE` | `/api/conferences/{id}` | Remove a conference (auth required). |

Responses are JSON-formatted with standard HTTP status codes (200, 201, 400, 401, 404, 500).

---

## Repository structure

```
.
├── README.md                          ← you are here
├── LICENSE                            ← MIT
├── .gitignore
├── public/                            ← web root
│   ├── index.php                      ← landing page
│   ├── conferences.php                ← listing page
│   ├── conference.php                 ← detail page
│   └── assets/                        ← CSS, JS, images
├── api/                               ← REST endpoints
│   ├── conferences.php
│   └── auth.php
├── includes/                          ← shared PHP modules
│   ├── db.php                         ← DB connection
│   └── helpers.php
├── sql/
│   └── schema.sql                     ← MySQL schema + seed data
└── docs/
    └── api_reference.md               ← full endpoint documentation
```

---

## Reproduce locally

### Prerequisites

- **PHP 8.0+** with `mysqli` extension
- **MySQL 8.0** or compatible (e.g. MariaDB 10.5+)
- A local web server: Apache, Nginx, or PHP's built-in dev server

### Setup

```bash
# 1. Clone
git clone https://github.com/nawafbalmutairi/conference-info-platform.git
cd conference-info-platform

# 2. Create the database
mysql -u root -p < sql/schema.sql

# 3. Configure DB credentials
cp includes/db.example.php includes/db.php
# edit includes/db.php with your MySQL credentials

# 4. Run the dev server
cd public
php -S localhost:8000
```

Open `http://localhost:8000` in your browser. The REST API is at `http://localhost:8000/api/conferences`.

---

## Tech stack

**Backend:** PHP 8 · MySQL 8
**Frontend:** HTML5 · CSS3 · vanilla JavaScript
**API:** REST · JSON
**Auth:** PHP session-based

---

## Author

**Nawaf Almutairi** — BSc Computer Science, Northumbria University · Class of 2026

[Portfolio](https://nawafbalmutairi.github.io) · [LinkedIn](https://linkedin.com/in/nawaf-almutairi-907766290/) · [Email](mailto:NawafBAlmutairi@outlook.sa)

---

## License

[MIT](LICENSE) — see file for full text.

# LeadScanner – SEO Automated & Lead Acquisition Toolkit

![Python](https://img.shields.io/badge/Python-3.11-blue?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.109-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-3.41-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-2.0-FF0000?style=for-the-badge&logo=sqlalchemy&logoColor=white)
![React](https://img.shields.io/badge/React-18.2-61DAFB?style=for-the-badge&logo=react&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.3-06B6D4?style=for-the-badge&logo=tailwind-css&logoColor=white)
![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup-4.12-FF9900?style=for-the-badge&logo=python&logoColor=white)

**LeadScanner** is an automated SEO analysis and lead prospecting tool designed to quickly identify business opportunities from any URL. This GitHub repository serves only as a showcase to demonstrate one of my personal projects. LeadScanner is currently under development and remains private for commercial purposes.

---

## About

**LeadScanner** combines a high-performance Python/FastAPI backend with a modern React frontend to offer a complete audit suite.

The project's goal is to:
* **Analyze** a website automatically to detect technical weaknesses (SEO).
* **Identifies** opportunities and threats for lead acquisition.
* **Log** audit history in a database to track progress over time.
* **Generate** actionable reports for freelancers, growth hackers, and data analysts.

---

## Features

### Complete SEO Analysis
The tool scans the target URL and verifies over 15 control points:

| Catégory | Checks Performed |
| :--- | :--- |
| **Meta & Content** | Title, Description, Tags H1, Language, Charset |
| **Technical** | Robots.txt, Sitemap.xml, HTTPS, Structure URL, Canonical |
| **Performance** | Server response time, Page weight |
| **Social & Mobile** | OpenGraph (og:title, og:desc), Twitter Cards, Viewport |
| **Off-Page** | Favicon detection, Backlinks (via API or free method) |

### Scoring & Reporting
* **Scoring Global :** Calculation of a weighted SEO health score.
* **Points Critiques :** Automatic generation of a summary of blocking errors.
* **Historique :** Automatic saving to SQLite (Tables `Company` and `SEOAudit`).

---

## Technical Architecture

The project relies on a decoupled (Headless) architecture:

* **Backend :** Python 3.13+, FastAPI, SQLAlchemy.
* **Frontend :** React 18, TailwindCSS, Framer Motion.
* **Database :** SQLite.
* **Analysis Engine :** BeautifulSoup4 & Requests (scripts situated in `backend/scripts/seo_analyzer/`).

**Data Flow :**
1.  The user sends a URL from the Frontend.
2.  FastAPI triggers the `seo_analyzer` module.
3.  The script downloads the page, extracts tags, detects errors, and calculates the score.
4.  Results are stored in the database.
5.  The Frontend retrieves the full JSON for display.

---

## Main API Endpoints

    POST /analyze-url : Launches an analysis and stores the result
    GET /audit/{company_id} : Retrieves details of a specific audit.
---

## Images
![Dashboard](dashboard.png)
![Onpage (sans api)](onpage.png)
![Offpage](offpage.png)

# 🎓 Django Student Attendance Management System

# Live Link: https://attenance-system.onrender.com

Developed with ❤️ by **Suman Anand**

[![Python Version](https://shields.io)](https://python.org)
[![Django Version](https://shields.io)](https://djangoproject.com)
[![License: MIT](https://shields.io)](https://opensource.org)
[![UI Framework](https://shields.io)](https://getbootstrap.com)

A modern, production-ready Django 5+ web application designed to streamline student attendance tracking, manage institutional announcements, and generate comprehensive analytical reports for schools or colleges.

---

## 🚀 Core Features

### 👥 User Roles & Authentication
* **Admin/Staff Dashboard:** Full administrative override capabilities to manage students, modify historical data, and monitor institutional analytics.
* **Student Portal:** Personalized dashboard allowing students to securely track their own chronological attendance percentages and view announcements.

### 📅 Attendance Tracking
* **Smart Daily Marking:** Intuitive interface for rapid attendance logging with built-in duplicate submittal protection.
* **Historical Accuracy:** Secure, non-destructive chronological logging system. Past records remain intact, editable only by authorized administrative users.
* **Persistent Archiving:** Historical records are permanently preserved; "resetting a new day" merely creates a fresh data capture sheet without altering old logs.

### 📢 Institutional Notice Board
* **Broadcast Hub:** Seamlessly publish updates, timetables, and alerts to the student community.
* **Priority Pinning:** Keep critical announcements anchored to the top of student feeds.

### 📊 Reports & Data Analytics
* **Visual Dashboards:** On-screen charts providing real-time data insights into attendance trends and metrics.
* **Multi-Format Exports:** One-click automated file generators compiling attendance logs into professional **PDF** layouts or structured **Excel** spreadsheets.

### 🎨 User Interface & Technical Base
* **Responsive Bootstrap 5 Design:** Fully adaptive grid layout optimized for desktops, tablets, and mobile devices.
* **Robust Database Integration:** Default plug-and-play SQLite environment for development with native PostgreSQL compatibility configured for cloud deployments.

---

## 🛠️ Technology Stack

* **Creator:** Suman Anand
* **Backend Framework:** Python / Django 5+
* **Frontend Interface:** HTML5, CSS3, JavaScript (ES6), Bootstrap 5
* **Database Engine:** SQLite (Local Dev) / PostgreSQL (Production ready)

---

## 🏃‍♂️ Quick Start Guide

Follow these steps to set up and launch your local development instance.

### 1. Environment Configuration
Clone the repository and jump into the project root directory:
```bash
git clone https://github.com
cd Attenance-System
```

Create a virtual isolated environment and install the required app packages:
```bash
# Windows
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### 2. Database Initialization
Generate your environment runtime values by duplicating the configuration sample:
```bash
cp .env.example .env
```
*(Open the new `.env` file and customize your secret configurations if necessary.)*

Run database migrations to initialize the schema:
```bash
python manage.py migrate
```

### 3. Account Creation & Seed Data
Generate your main administrative login access credentials:
```bash
python manage.py createsuperuser
```

*(Optional)* Inject demo database entries to populate charts and tables instantly:
```bash
python manage.py seed_demo_data
```

### 4. Run the Server
Launch your local web engine node:
```bash
python manage.py runserver
```
The application will now be live and accessible at **`http://127.0.0`**.

---

## 🗺️ System URL Architecture



| URL Path | Target Resource | Authorization Access |
| :--- | :--- | :--- |
| `/accounts/login/` | Universal Login Workspace | All Users |
| `/admin-dashboard/` | High-Level Analytical Control Hub | Staff / Superusers Only |
| `/student-dashboard/` | Individual Metric Tracking Sheet | Authenticated Students |
| `/students/` | Complete Student Directory & Search View | Administrative Staff |
| `/attendance/` | Active Log Submission Terminal | Administrative Staff |
| `/notices/` | Announcement Panel and Configuration Sheet | Public Read / Admin Write |
| `/reports/` | PDF & Excel Engine Export Endpoint | Administrative Staff |

---

## ⚙️ Data Architecture Notes

* **Data Modeling:** Authentication models link directly to separate profile definitions via `Student.user` endpoints. Staff privileges map directly onto native Django authentication tags (`is_staff`).
* **Relational Security:** Attendance objects register individual records uniquely mapped via a deterministic `(student_id, date)` layout.

---

## 🌐 Production Deployment Requirements

When migrating this application away from your local development environment into live hosting environments (e.g., AWS, Heroku, DigitalOcean), ensure you implement the following adjustments:

1. **Database:** Set up a live cloud database and provide its access connection string inside the `DATABASE_URL` environment flag to automatically route through the PostgreSQL backend connector.
2. **Security:** Update the `.env` context variables to declare `DEBUG=False` and assign your custom production domains inside the `ALLOWED_HOSTS` whitelist array.
3. **Static Assets:** Run `python manage.py collectstatic` and utilize custom web servers (like Nginx, Apache) or storage engines (like AWS S3 or WhiteNoise) to securely serve application media files.

---

## 👨‍💻 About the Author

* **Developer:** Suman Anand
* **GitHub:** [@sumananand460](https://github.com)

---

## 📄 License

Distributed under the MIT License. Copyright (c) 2026 Suman Anand

# 🅿️ Simple Parking Management System

[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-Web%20Framework-000?logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![MySQL](https://img.shields.io/badge/Database-MySQL-4479A1?logo=mysql&logoColor=white)](https://www.mysql.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A lightweight, Flask-based web application to manage parking slot bookings. Users can register, log in, and reserve parking slots with custom time ranges, while administrators get a full dashboard to oversee all bookings and resolve slot conflicts.

---

## 📖 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Database Schema](#-database-schema)
- [Getting Started](#-getting-started)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [License](#-license)
- [Contributing](#-contributing)

---

## ✨ Features

- 🔐 **User Authentication** — Register and log in with username, email, and password.
- 🅿️ **Slot Booking** — Book an available parking slot by selecting start and end times.
- ⏱️ **Conflict Detection** — Prevents overlapping bookings for the same slot and time window.
- 🗺️ **Parking Map** — View available slots on a map interface.
- 👨‍💼 **Admin Dashboard** — Admins can view all user bookings and manage slot assignments.
- 📤 **Drop Booking** — Release your booked slot when done.
- 🚪 **Session Management** — Secure login sessions with logout functionality.

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| Backend | Python, Flask, Flask-MySQLdb |
| Database | MySQL |
| Frontend | HTML5, CSS3, Jinja2 Templates |
| Server | Flask development server |

---

## 🗄️ Database Schema

The app uses a MySQL database named **`parkin`** with a `user` table:

| Column | Type | Description |
|--------|------|-------------|
| `id` | VARCHAR | Unique booking identifier (`username + slot`) |
| `username` | VARCHAR | Registered user's username |
| `mail` | VARCHAR | User's email address |
| `password` | VARCHAR | User's password |
| `slot` | VARCHAR | Assigned parking slot |
| `start` | TIME | Booking start time |
| `end` | TIME | Booking end time |

Create the database and table before running the app:

```sql
CREATE DATABASE parkin;
USE parkin;

CREATE TABLE user (
    id VARCHAR(100),
    username VARCHAR(100),
    mail VARCHAR(100),
    password VARCHAR(100),
    slot VARCHAR(50),
    start TIME,
    end TIME
);
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10 or higher
- MySQL Server running locally
- `pip` package manager

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/Simple-Parking-Management-System.git
   cd Simple-Parking-Management-System
   ```

2. **Create and activate a virtual environment**
   ```bash
   # Windows
   python -m venv venv
   venv\Scripts\activate

   # macOS / Linux
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install flask flask-mysqldb
   ```

4. **Configure MySQL**
   Update the MySQL credentials in `app.py` if needed:
   ```python
   app.config['MYSQL_HOST'] = '0.0.0.0'
   app.config['MYSQL_USER'] = 'root'
   app.config['MYSQL_PASSWORD'] = 'password'
   app.config['MYSQL_DB'] = 'parkin'
   ```

5. **Run the application**
   ```bash
   python app.py
   ```

   The app will be available at `http://127.0.0.1:5000/`.

---

## 💻 Usage

1. Open `http://127.0.0.1:5000/` in your browser.
2. **Register** a new account or **log in** with existing credentials.
3. Admin login: username `admin`, password `admin@123`.
4. From the dashboard, select a parking slot and time range to book.
5. Admins can view all bookings and manage slots via the admin dashboard.
6. Use **Drop** to release your booking or **Logout** to end your session.

---

## 📁 Project Structure

```
Simple-Parking-Management-System/
├── app.py                 # Main Flask application
├── .gitignore             # Git ignore rules
├── static/                # Static assets (CSS, images, JS)
└── templates/             # Jinja2 HTML templates
    ├── index.html
    ├── admindashboard.html
    └── parkmap.html
```

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 🤝 Contributing

Contributions are welcome! Feel free to fork the repo, open issues, and submit pull requests.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

---

## 🙌 Acknowledgments

- [Flask](https://flask.palletsprojects.com/) — Python web framework
- [MySQL](https://www.mysql.com/) — Relational database
- Open source community for tools and resources
# 🏠 Smart Home Automation System

A Python desktop application for managing smart home devices, automations, maintenance logs, and usage analytics. Built with **Tkinter** for the GUI and **MySQL** as the backend, it features role-based access, advanced automation scheduling, and real-time logging via triggers and functions.

---

## 🚀 Features

- 🔐 **User Authentication & Roles**: Admin (full access) and User (view-only), securely managed in MySQL.
- 💡 **Device Management**: Add, view, and toggle smart devices with automatic status logging via triggers.
- 🕒 **Automation Rules** (Admin only): Schedule devices with validated start/end times.
- 🛠️ **Maintenance Tracking**: Log issues, track history, and auto-schedule next maintenance.
- 📊 **Activity Logs**: Summarized usage stats calculated using advanced SQL queries.
- 🖥️ **Intuitive GUI**: Built using Tkinter with easy navigation and clear functionality.

---

## 🧰 Technologies Used

- **Python** 🐍
- **Tkinter** – Desktop GUI
- **PyMySQL** – Database connector
- **MySQL** – Relational database with triggers & functions
- **dateutil / datetime** – Time calculations for logs & maintenance

---

## 🛠️ Database Overview

The backend uses a **normalized MySQL database design**, ensuring data integrity, minimal redundancy, and efficient relational mappings.

- `User`: Stores authentication, role, and profile info.
- `Device`: Tracks each smart device and status.
- `Automation`: Defines device schedules.
- `Maintenance`: Logs service history and auto-calculates next due.
- `Logs`: Automatically updated device activity (via MySQL triggers).

### 🔁 Triggers & Functions

- `authenticate_user()`: Returns user role based on credentials.
- `before_device_activate`: Logs start time when device is activated.
- `after_device_deactivate`: Calculates and stores usage duration when turned off.

---

## 📦 Installation

```bash
git clone https://github.com/Janvi-M/Smart-Home-Automation-System-Using-MySQL-and-Python/
cd smart-home-automation
pip install pymysql python-dateutil
```

---

## 🛠️ MySQL Setup

```sql
CREATE DATABASE smart_home;
-- Create tables and sample data (see full schema in README)
-- Create 'newuser' and grant privileges
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'your_password';
GRANT ALL PRIVILEGES ON smart_home.* TO 'newuser'@'localhost';
FLUSH PRIVILEGES;
```

Update `python_script.py`:

```python
connection = pymysql.connect(
    host='localhost',
    user='newuser',
    password='your_password',
    database='smart_home'
)
```

---

## ▶️ Usage

```bash
python python_script.py
```

- 👤 **Login/Signup** with `admin1/adminpass` or `user1/userpass`
- 🛠️ **Admins** can manage automations, maintenance, and logs
- 👁️ **Users** can view devices and automation schedules



## 🔮 Future Enhancements

- 💾 MySQL Stored Procedures for business logic
- 🔐 Password hashing (e.g., bcrypt)
- 🌐 API integration with real devices
- 📬 Email or system notifications
- 📈 More analytics and performance dashboards
- 🎨 Enhanced Tkinter UI styling

---

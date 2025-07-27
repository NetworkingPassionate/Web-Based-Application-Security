# Web-Based-Application-Security


# 🧨 SQL Injection Demo – Educational Lab Environment

This repository presents a controlled, ethical demonstration of a **SQL Injection** vulnerability. The goal is to showcase how poorly validated user input can compromise backend databases — and more importantly, how to **detect, prevent, and mitigate** such issues in real-world environments.

> ⚠️ This demo is strictly for **educational** purposes. All testing is conducted in a local environment with non-production data. Do not use this attack on systems you do not own or have explicit permission to test.

---

## 🧪 Demo Overview

- **Attack Type**: Classic SQL Injection via a vulnerable web form
- **Target Stack**: Flask (Python) web app with SQLite database
- **Injection Vector**: Unescaped user input passed into SQL query
- **Outcome**: Unauthorized access to user data

---

## 🛠 Project Setup

```bash
git clone https://github.com/yourusername/sql-injection-demo.git
cd sql-injection-demo
pip install -r requirements.txt
python app.py

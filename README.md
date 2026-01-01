# CMPT 310 — Lab 3  
**SQL, PHP, JSON & Google Charts**

**Student:** Franklin Safari  
**Student ID:** 210203  
**Files:** `lab3.php`, `lab3.sql`, `index.html`, `*.html reports`, `lab3.css`

---

## Overview

This lab demonstrates the integration of **database systems and web technologies** by building a small data-driven web application using **MySQL**, **PHP (mysqli)**, **JSON**, **jQuery**, and the **Google Charts API**.

The application queries a relational database about piano technicians, inspections, pianos, and models, converts query results into **JSON**, and visualizes the data using interactive charts and reports in the browser.

---

## Learning Objectives

- Write SQL queries against a relational database
- Connect PHP to MySQL using `mysqli`
- Generate JSON dynamically from database query results
- Consume JSON data in JavaScript
- Visualize data using Google Charts
- Build simple data-driven web reports

---

##Technologies used
-MYSQL, PHP(mysqli), SQL, JSON, JavaScript, jQuerry, Google Charts API, HTML & CSS

## File Descriptions

### `lab3.sql`
- Creates and populates the **Lab3** database.
- Defines tables including:
  - `Technician`
  - `Inspection`
  - `Piano`
  - `Model`
- Establishes:
  - Primary keys
  - Foreign keys
  - Referential integrity constraints
- Inserts sample data for testing and reporting.

### `lab3.php`
- Acts as the **server-side data API**.
- Connects to the MySQL database using `mysqli`.
- Exposes three JSON endpoints via PHP functions:
  - **`orgJSON()`**  
    - Returns technician hierarchy data for an organizational chart.
  - **`technicianJSON()`**  
    - Returns the top *N* technicians by number of inspections.
  - **`pianoJSON()`**  
    - Returns piano model sales counts by year range.
- Outputs JSON formatted specifically for **Google Charts**.

### `index.html`
- Entry point for the lab.
- Provides links to report pages:
  - Piano Technician Organizational Chart
  - Piano Model Sales by Year
  - Top Piano Technicians
- Uses standard HTML and CSS for layout and navigation.

### Report Pages (`orgReport.html`, `pianoReport.html`, `technicianReport.html`)
- Use **JavaScript**, **jQuery**, and **Google Charts API**.
- Fetch JSON data asynchronously from `lab3.php`.
- Render charts dynamically in the browser.

---

## Database Structure Summary

- **Technician**
  - Self-referencing foreign key to represent supervisor relationships.
- **Inspection**
  - Links technicians to pianos and inspection results.
- **Piano**
  - References piano models and manufacturing dates.
- **Model**
  - Stores piano model information.

The schema demonstrates **one-to-many**, **many-to-one**, and **recursive** relationships.

---

## How to Run the Lab

### 1. Set up the database
```bash
mysql -u <user> -p < lab3.sql

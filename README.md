# 🧳 Travel Booking Management System

A robust and scalable travel booking management system simulating a real-world multi-modal travel platform using SQL and relational database principles. It enables seamless management of customers, bookings, transportation, and payments — all within a centralized system.

---

## 🚀 Project Overview

This project provides a one-stop database system for handling complex travel logistics involving flights, trains, buses, cruises, and cars. Built with a fully normalized SQL schema, it ensures accurate, efficient, and flexible travel data handling.

---

## 🗂️ Features

- 👤 Customer and identity management
- 👨‍💼 Employee and department tracking
- 🌐 Centralized destination database
- 🚌 Multi-transport support (Flights, Trains, Buses, Cruises, Cars)
- 💳 Secure payment tracking
- 📦 Complete booking and reservation management

---

## 🧱 Database Design

### 🔑 Core Tables

- `CustomerDetails_reneeka`
- `Employee_reneeka`
- `Destination`
- `Payment_chahel`
- `Booking_chahel`

### 🚗 Transport Tables

- `Flights_amishi`
- `Trains_reneeka`
- `Buses_amishi`
- `Cruise_amishi`
- `Car_chahel`

---

## 🔗 Relationships

- One-to-Many: Customers → Payments, Bookings
- One-to-Many: Destination → Transport Modes
- Many-to-Many: Employee ↔ Transport
- Booking ↔ Customer ↔ Payment with foreign key integrity

---

## 🧠 Normalization

- ✅ **1NF**: Atomic attributes and unique records
- ✅ **2NF**: No partial dependencies
- ✅ **3NF**: No transitive dependencies
- ✅ **BCNF**: Every determinant is a candidate key

---

## 🛠️ Tech Stack

| Layer       | Tools Used           |
|-------------|----------------------|
| Language    | SQL (MySQL)          |
| Platform    | MySQL Workbench      |
| Project Type| Relational DB Design |

---

## 🧪 Sample SQL Queries

```sql
-- 1. Total income
SELECT SUM(PaymentAmount) AS Total_Income FROM Payment_chahel;

-- 2. Most used transport
SELECT Transport, COUNT(*) AS UsageCount 
FROM Booking_chahel 
GROUP BY Transport 
ORDER BY UsageCount DESC LIMIT 1;

-- 3. Create view for booking summary
CREATE VIEW Booking_Summary AS 
SELECT COUNT(*) AS TotalBookings,
       SUM(p.PaymentAmount) AS TotalPaid,
       AVG(p.PaymentAmount) AS AvgPaid
FROM Booking_chahel b
JOIN Payment_chahel p ON b.PaymentID = p.PaymentID;

---
```

## 📸 ERD & Diagrams

Entity-Relationship and Relational Diagrams are included to visualize:
- Entity relationships
- Cardinality and participation
- Primary and foreign key connections

> *(You can include images here with: `![ERD](images/ERD.png)`)*

---

## 🧠 Learnings

- End-to-end relational schema design
- Implementation of BCNF normalization
- Use of SQL joins, views, constraints, and aggregations
- Optimization of complex, real-world travel queries

---

## 🚧 Challenges Faced

- Designing scalable schema across multiple transport types
- Ensuring integrity across customer-booking-payment pipelines
- Managing constraints, default values, and validations
- Implementing business logic (e.g., valid destination mapping)

---

## 🔮 Future Enhancements

- Web-based frontend using Flask/Django
- Admin dashboard for bookings and transactions
- Cloud deployment of MySQL server
- Real-time seat and route availability tracker

---

## 👨‍💻 Author

**Aashutosh Yadav**  
National Institute of Technology, Bhopal  
*Database Developer | SQL Enthusiast | Systems Architect*

---

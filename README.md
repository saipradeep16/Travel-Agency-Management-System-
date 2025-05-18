# 🌍 Travel Agency Management System

This project is a relational database solution developed as part of the INFO 5707 course at the University of North Texas. It is designed to enhance the operational efficiency and booking experience for travel agencies and customers by managing reservations, travel services, providers, destinations, and accommodations.

---

## 📌 Project Overview

The Travel Agency Management System simplifies travel bookings by offering a user-friendly and centralized platform. It empowers both customers and agency staff with real-time service availability, seamless booking, and secure payment processing. The system covers a variety of services including flights, transportation, hotels, and tours — all connected through a structured database model.

---

## 🧠 Features

- Unique booking ID for each reservation
- Real-time inventory visibility for staff and customers
- Centralized customer and provider management
- Seamless status updates for bookings
- Secure payment processing in USD
- English as the primary transaction language
- Support for sustainable and responsible travel planning

---

## 🎯 Objectives

- Guarantee easy and customized travel experiences
- Forecast and plan future travel trends
- Prevent overbooking and underbooking
- Optimize inventory utilization and profitability
- Maintain operational transparency and data security

---

## 🛠️ Technology Stack

- **Database**: MySQL
- **Query Language**: SQL
- **Tools**: MySQL Workbench, ER Diagrams

---

## 🗃️ Core Database Tables

- `Customers`
- `Bookings`
- `Services`
- `Destinations`
- `Accommodations`
- `Providers`

---

## 💻 SQL Query Examples

```sql
-- 1. List all Confirmed Bookings
SELECT BookingID, CustomerID, BookingDate, PaymentAmount
FROM Bookings
WHERE Status = 'Confirmed';

-- 2. Bookings with Payment Above a Certain Amount
SELECT BookingID, CustomerID, BookingDate, PaymentAmount
FROM Bookings
WHERE PaymentAmount > 400;

-- 3. Services Provided by a Specific Provider (ProviderID = 1)
SELECT ServiceID, ServiceType, Description, Price
FROM Services
WHERE ProviderID = 1;

-- 4. Accommodations at a Specific Destination (DestinationID = 1)
SELECT a.AccommodationID, a.Name, a.MaxCapacity
FROM Accommodations a
WHERE a.DestinationID = 1;

-- 5. Total Payment Made by a Specific Customer (CustomerID = 1)
SELECT c.CustomerID, c.FirstName, c.LastName, SUM(b.PaymentAmount) as TotalPayment
FROM Customers c
JOIN Bookings b ON c.CustomerID = b.CustomerID
WHERE c.CustomerID = 1
GROUP BY c.CustomerID, c.FirstName, c.LastName;

-- 6. Retrieve all Services from Services Table
SELECT * FROM Services;

# 🌍 Travel Agency Management System

This project is a relational database solution developed as part of the INFO 5707 course at the University of North Texas. It is designed to enhance the operational efficiency and booking experience for travel agencies and customers by managing reservations, travel services, providers, destinations, and accommodations.

---

## 📌 Project Overview

The Travel Agency Management System simplifies travel bookings by offering a user-friendly and centralized platform. It empowers both customers and agency staff with real-time service availability, seamless booking, and secure payment processing. The system covers a variety of services including flights, transportation, hotels, and tours — all connected through a structured database model.

---

## 🛠️ Technologies Used

- **Database**: MySQL  
- **Language**: SQL  
- **Tools**: MySQL Workbench, ER Diagrams

---

## 🧠 Features

- Unique booking ID for each reservation  
- Real-time inventory tracking for destinations, services, and accommodations  
- Role-based access for staff to manage reservations and services  
- Support for secure payments in USD  
- Organized data for analytics and reporting  
- English as the primary language for operations and transactions  

---

## 📂 Database Tables

- `Customers`  
- `Bookings`  
- `Services`  
- `Destinations`  
- `Accommodations`  
- `Providers`

---

## 💻 SQL Query Examples

### 1️⃣ List all Confirmed Bookings
```sql
SELECT BookingID, CustomerID, BookingDate, PaymentAmount
FROM Bookings
WHERE Status = 'Confirmed';
```

---

### 2️⃣ Bookings with Payment Above a Certain Amount
```sql
SELECT BookingID, CustomerID, BookingDate, PaymentAmount
FROM Bookings
WHERE PaymentAmount > 400;
```

---

### 3️⃣ Services Provided by a Specific Provider
```sql
SELECT ServiceID, ServiceType, Description, Price
FROM Services
WHERE ProviderID = 1;
```

---

### 4️⃣ Accommodations at a Specific Destination
```sql
SELECT a.AccommodationID, a.Name, a.MaxCapacity
FROM Accommodations a
WHERE a.DestinationID = 1;
```

---

### 5️⃣ Total Payment Made by a Specific Customer
```sql
SELECT c.CustomerID, c.FirstName, c.LastName, SUM(b.PaymentAmount) as TotalPayment
FROM Customers c
JOIN Bookings b ON c.CustomerID = b.CustomerID
WHERE c.CustomerID = 1
GROUP BY c.CustomerID, c.FirstName, c.LastName;
```

## 🧾 Conclusion

Through this project, we investigated the complexities involved in managing customer bookings, service coordination, and travel agency logistics. We focused on developing a robust relational database design tailored to modern travel needs and future scalability.

The project demonstrated that a properly structured relational database can efficiently manage key aspects of a travel agency — from customers and bookings to services and providers. By implementing SQL queries, we were able to retrieve valuable insights such as booking statuses, payment summaries, and service availability, enabling data-driven decision-making and efficient operations.

The system ensured data accuracy, minimized redundancy, and allowed for advanced query execution through the use of primary and foreign keys. It has the potential to integrate with external systems like airline APIs and be extended with machine learning capabilities to predict customer preferences and demand trends.

Overall, the Travel Agency Management System serves as a scalable and efficient solution for digital transformation in the tourism and travel industry.



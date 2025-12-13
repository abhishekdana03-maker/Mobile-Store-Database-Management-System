# Mobile-Store-Database-Management-System

## 📌 Project Objective: Mobile Store Database Management System

The main objective of this project is to design and implement a structured MySQL database that efficiently manages all operations of a mobile store. This system aims to store, organize, and retrieve information related to mobiles, stock, customers, and sales in a reliable and user-friendly manner.

# Key Objectives:

 ### 1)Efficient Data Storage  
   - To store details of mobile phones, customers, stock levels, and sales transactions in well-designed relational tables.

 ### 2)Easy Data Retrieval
 
  - To enable fast and accurate retrieval of information such as available stock, customer details, and sales history using SQL queries.

 ### 3)Inventory Management
 
  - To track the stock of each mobile model and update quantities based on sales to prevent over-selling or stock shortages.

 ### 4)Sales Monitoring
 
  - To maintain complete sales records including customer, product, quantity, and sale date for business analysis.

 ### 5)Customer Management
 
  - To store and manage customer information for sales tracking, communication, and service.

 ### 6)Data Integrity & Consistency
 
  - To ensure accuracy using:
     - Primary keys
     - Foreign keys
     - Proper relationships between tables

 ### 7)Reporting & Analysis
 
  - To generate meaningful insights such as:
     - Top-selling mobiles
     - Total sales revenue
     - Low-stock alerts
     - Purchase history of customers

 ### 8)Real-World Business Simulation
 
   - To simulate a real mobile shop’s operations through a database that can be used for practical learning and project demonstration.     <br>


   </br>


# 🔁 Project Workflow: Mobile Store Database Management System

### 1. System Initialization
- Create the database in MySQL.
  - Define tables:
    - mobiles
    - stocks
    - customers
    - sales
Set Primary Keys and Foreign Key relationships to maintain data integrity.

### 2. Mobile Data Entry
- Insert mobile phone details into the mobiles table:
  - Brand
  - Model
  - RAM
  - Storage
  - Price
Each mobile is uniquely identified by mobile_id.

### 3. Stock Management
- Insert stock information into the 'stocks' table.
- Link stock records to mobiles using 'mobile_id' (Foreign Key).
- Maintain available 'quantity' for each mobile model.

### 4. Customer Registration 
- Store customer details in the customers table:
  - Name
  - Phone number
  - Email
Assign a unique customer_id to each customer.

### 5. Sales Transaction Process
- When a customer purchases a mobile:
  1. Customer is selected from the customers table.
  2.  Mobile is selected from the mobiles table.
  3.   Quantity and sale date are recorded in the sales table.
- Each sale links:
  - Customer → customer_id
  - Mobile → mobile_id

### 6. Stock Update After Sale 
- After a sale:
  - Stock quantity is reduced based on the number of units sold.
  - Ensures real-time inventory tracking.

### 7. Data Validation & Integrity
- Foreign keys ensure:
  - Only existing mobiles can be sold.
  - Only registered customers can make purchases.
- Prevents invalid or duplicate records.

### 8. Data Retrieval & Reporting
- Generate reports using SQL queries:
  - Available stock report
  - Sales summary
  - Customer purchase history
  - Top-selling mobiles
  - Low-stock alerts

### 9. Business Analysis
- Analyze sales trends based on:
  - Brand
  - Model
  - Date range
- Support decision-making for restocking and pricing.

### 10. System Maintenance
- Update mobile prices if required.
- Add new mobile models.
- Remove discontinued products.
- Maintain historical sales records.


## -> some queries on this project
### 1️⃣ Display all mobile brands and their models
```SELECT brand, model FROM mobiles;```


Result: Displays all available mobile brands with their respective models.

2️⃣ Customers who purchased a mobile on 2025-01-10
SELECT c.name
FROM customers c
JOIN sales s ON s.customer_id = c.customer_id
WHERE s.sale_date = '2025-01-10'
GROUP BY c.name;


Result: Rahul Sharma

3️⃣ Customers who bought an Apple mobile
SELECT c.name, c.email
FROM customers c
JOIN sales s ON s.customer_id = c.customer_id
JOIN mobiles m ON m.mobile_id = s.mobile_id
WHERE m.brand = 'Apple';

4️⃣ Sales details with customer name and mobile model
SELECT s.*, c.name, m.model
FROM sales s
JOIN customers c ON c.customer_id = s.customer_id
JOIN mobiles m ON m.mobile_id = s.mobile_id;

5️⃣ Stock details with mobile brand and model
SELECT m.brand, m.model, st.stock
FROM mobiles m
JOIN stocks st ON st.mobile_id = m.mobile_id;

6️⃣ Customers who bought Samsung mobiles
SELECT c.name
FROM customers c
JOIN sales s ON s.customer_id = c.customer_id
JOIN mobiles m ON m.mobile_id = s.mobile_id
WHERE m.brand = 'Samsung';

7️⃣ Total number of mobiles sold
SELECT SUM(quantity) AS total_sold_mobiles FROM sales;


Result: 26 mobiles sold

8️⃣ Stock count for each brand
SELECT m.brand, SUM(st.stock) AS total_stock
FROM mobiles m
JOIN stocks st ON st.mobile_id = m.mobile_id
GROUP BY m.brand;

9️⃣ Total sales quantity by brand
SELECT m.brand, SUM(s.quantity) AS total_sold
FROM mobiles m
JOIN sales s ON s.mobile_id = m.mobile_id
GROUP BY m.brand;

🔟 Total revenue generated by each brand
SELECT m.brand, SUM(m.price * s.quantity) AS brand_revenue
FROM mobiles m
JOIN sales s ON s.mobile_id = m.mobile_id
GROUP BY m.brand;

1️⃣1️⃣ Mobiles priced above ₹50,000
SELECT brand, model, price
FROM mobiles
WHERE price > 50000
ORDER BY price DESC;

1️⃣2️⃣ Customers who bought more than one quantity
SELECT c.name, s.quantity
FROM customers c
JOIN sales s ON s.customer_id = c.customer_id
WHERE s.quantity > 1;

1️⃣3️⃣ Mobiles that are out of stock
SELECT m.brand, m.model, m.price
FROM mobiles m
JOIN stocks st ON st.mobile_id = m.mobile_id
WHERE st.stock = 0;

1️⃣4️⃣ Mobiles priced higher than the average price
SELECT brand, model, price
FROM mobiles
WHERE price > (SELECT AVG(price) FROM mobiles);


Average price: ₹43,665

1️⃣5️⃣ Customer who bought the most expensive mobile
SELECT DISTINCT c.name, m.price
FROM customers c
JOIN sales s ON s.customer_id = c.customer_id
JOIN mobiles m ON m.mobile_id = s.mobile_id
WHERE m.price = (
  SELECT MAX(price)
  FROM mobiles m
  JOIN sales s ON s.mobile_id = m.mobile_id
);


Result: Rahul Sharma – ₹79,999


## the workflow diagram image
  
<img width="200" height="1536" alt="7e39c3a1-a2a9-4659-87de-0b89b331f880" src="https://github.com/user-attachments/assets/54593e43-ee6e-4e4b-b081-00bbae6eb194" />

# 📌Conclusion

The Mobile Store Database Management System efficiently manages mobile details, stock, customers, and sales using MySQL. It ensures data accuracy, easy retrieval, and proper inventory tracking, making it suitable for learning real-world database applications.




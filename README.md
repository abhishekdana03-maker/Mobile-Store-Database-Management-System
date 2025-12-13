# Mobile-Store-Database-Management-System

## 📌 Project Objective: Mobile Store Database Management System

The main objective of this project is to design and implement a structured MySQL database that efficiently manages all operations of a mobile store. This system aims to store, organize, and retrieve information related to mobiles, stock, customers, and sales in a reliable and user-friendly manner.

# Key Objectives:

 ## 1)Efficient Data Storage  
   - To store details of mobile phones, customers, stock levels, and sales transactions in well-designed relational tables.

 ## 2)Easy Data Retrieval
 
  - To enable fast and accurate retrieval of information such as available stock, customer details, and sales history using SQL queries.

 ## 3)Inventory Management
 
  - To track the stock of each mobile model and update quantities based on sales to prevent over-selling or stock shortages.

 ## 4)Sales Monitoring
 
  - To maintain complete sales records including customer, product, quantity, and sale date for business analysis.

 ## 5)Customer Management
 
  - To store and manage customer information for sales tracking, communication, and service.

 ## 6)Data Integrity & Consistency
 
  - To ensure accuracy using:
     - Primary keys
     - Foreign keys
     - Proper relationships between tables

 ## 7)Reporting & Analysis
 
  - To generate meaningful insights such as:
     - Top-selling mobiles
     - Total sales revenue
     - Low-stock alerts
     - Purchase history of customers

 ## 8)Real-World Business Simulation
 
   - To simulate a real mobile shop’s operations through a database that can be used for practical learning and project demonstration.     <br>


   </br>


# 🔁 Project Workflow: Mobile Store Database Management System

## 1. System Initialization
- Create the database in MySQL.
  - Define tables:
    - mobiles
    - stocks
    - customers
    - sales
Set Primary Keys and Foreign Key relationships to maintain data integrity.

## 2. Mobile Data Entry
- Insert mobile phone details into the mobiles table:
  - Brand
  - Model
  - RAM
  - Storage
  - Price
Each mobile is uniquely identified by mobile_id.

## 3. Stock Management
-Insert stock information into the 'stocks' table.
-Link stock records to mobiles using 'mobile_id' (Foreign Key).
-Maintain available 'quantity' for each mobile model.

4. Customer Registration

Store customer details in the customers table:

Name

Phone number

Email

Assign a unique customer_id to each customer.

5. Sales Transaction Process

When a customer purchases a mobile:

Customer is selected from the customers table.

Mobile is selected from the mobiles table.

Quantity and sale date are recorded in the sales table.

Each sale links:

Customer → customer_id

Mobile → mobile_id

6. Stock Update After Sale

After a sale:

Stock quantity is reduced based on the number of units sold.

Ensures real-time inventory tracking.

7. Data Validation & Integrity

Foreign keys ensure:

Only existing mobiles can be sold.

Only registered customers can make purchases.

Prevents invalid or duplicate records.

8. Data Retrieval & Reporting

Generate reports using SQL queries:

Available stock report

Sales summary

Customer purchase history

Top-selling mobiles

Low-stock alerts

9. Business Analysis

Analyze sales trends based on:

Brand

Model

Date range

Support decision-making for restocking and pricing.

10. System Maintenance

Update mobile prices if required.

Add new mobile models.

Remove discontinued products.

Maintain historical sales records.



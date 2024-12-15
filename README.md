# Ola Data Analysis Project 🚖

![Project Logo](https://github.com/sateeshVFX/Ola-Data-Analysis/blob/main/Ola/Logo.png)  <!-- Replace with a relevant image or logo URL -->

## Project Overview 🌟

This project involves the analysis of ride booking data generated for Bengaluru city over the course of one month. The dataset consists of various attributes related to bookings, including booking status, customer ratings, vehicle types, and reasons for ride cancellations. The goal is to derive insights using SQL queries and visualize data through Power BI.

---

## Dataset  📊

The dataset contains **1,00,000 rows** with the following columns:

- **Date**
- **Time**
- **Booking ID**
- **Booking Status** (Success, Cancelled by Customer, Cancelled by Driver, Incomplete)
- **Customer ID**
- **Vehicle Type** (Auto, Prime Plus, Prime Sedan, Mini, Bike, eBike, Prime SUV)
- **Pickup Location** (Dummy locations in Bangalore)
- **Drop Location** (Taken from dummy pickup locations)
- **Avg VTAT** (Avg. Time taken to arrive at the vehicle)
- **Avg CTAT** (Avg. Time taken to arrive at the Customer)
- **Cancelled Rides by Customer**
- **Reason for Canceling by Customer** (Various reasons)
- **Cancelled Rides by Driver**
- **Incomplete Rides**
- **Incomplete Rides Reason** (Various reasons)
- **Booking Value**
- **Ride Distance**
- **Driver Ratings**
- **Customer Rating**

---

## SQL Analysis 📝

### SQL Questions
1. Retrieve all successful bookings.
2. Find the average ride distance for each vehicle type.
3. Get the total number of cancelled rides by customers.
4. List the top 5 customers who booked the highest number of rides.
5. Get the number of rides cancelled by drivers due to personal and car-related issues.
6. Find the maximum and minimum driver ratings for Prime Sedan bookings.
7. Retrieve all rides where payment was made using UPI.
8. Find the average customer rating per vehicle type.
9. Calculate the total booking value of rides completed successfully.
10. List all incomplete rides along with the reason.

### SQL Answers
```sql
1. SELECT * FROM bookings WHERE Booking_Status = 'Success';

2. SELECT Vehicle_Type, AVG(Ride_Distance) AS avg_distance FROM bookings GROUP BY Vehicle_Type;

3. SELECT COUNT(*) FROM bookings WHERE Booking_Status = 'Cancelled by Customer';

4. SELECT Customer_ID, COUNT(Booking_ID) AS total_rides FROM bookings GROUP BY Customer_ID ORDER BY total_rides DESC LIMIT 5;

5. SELECT COUNT(*) FROM bookings WHERE Cancelled_Rides_by_Driver = 'Personal & Car related issue';

6. SELECT MAX(Driver_Ratings) AS max_rating, MIN(Driver_Ratings) AS min_rating FROM bookings WHERE Vehicle_Type = 'Prime Sedan';

7. SELECT * FROM bookings WHERE Payment_Method = 'UPI';

8. SELECT Vehicle_Type, AVG(Customer_Rating) AS avg_customer_rating FROM bookings GROUP BY Vehicle_Type;

9. SELECT SUM(Booking_Value) AS total_successful_value FROM bookings WHERE Booking_Status = 'Success';

10. SELECT Booking_ID, Incomplete_Rides_Reason FROM bookings WHERE Incomplete_Rides = 'Yes';
```

# Power BI Dashboard for Ride-Sharing Data

## Overview

This repository contains a Power BI dashboard that provides comprehensive insights into ride-sharing data. The dashboard consists of five pages, each focused on critical metrics related to ride volume, revenue, cancellation reasons, customer and driver ratings, and vehicle types.

## Dashboard Pages

### Page 1: Overview
- **Description**: A comprehensive snapshot of ride-sharing metrics, including total rides, overall revenue, and basic performance indicators.
-   Overview
-   ![Overview](https://github.com/sateeshVFX/Ola-Data-Analysis/blob/main/Ola/Dashboard-Overall.png) 

### Page 2: Vehicle Type
- **Description**: A representation of vehicle types utilized in the ride-sharing service, including performance metrics like average distance traveled and ratings.
- Vehicle Type
- ![Vehicle Type](https://github.com/sateeshVFX/Ola-Data-Analysis/blob/main/Ola/Dashboard-Vehicle.png)

### Page 3: Revenue
- **Description**: A detailed visualization of revenue generated from rides, categorized by various factors such as time periods, payment methods, and customer demographics.
- Revenue
- ![Revenue](https://github.com/sateeshVFX/Ola-Data-Analysis/blob/main/Ola/Dashboard-Revenue.png)

### Page 4: Cancellation
- **Description**: A breakdown of ride cancellations showing the reasons behind cancellations and their frequency, allowing stakeholders to identify patterns and areas for improvement.
- Cancellation
- ![Cancellation](https://github.com/sateeshVFX/Ola-Data-Analysis/blob/main/Ola/Dashboard-Cancellation.png)

### Page 5: Ratings
- **Description**: A detailed analysis of driver and customer ratings, showcasing average ratings by vehicle type and other metrics to gauge service quality.
- Ratings
- ![Ratings](https://github.com/sateeshVFX/Ola-Data-Analysis/blob/main/Ola/Dashboard-Ratings.png)



## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/your-repo-name.git

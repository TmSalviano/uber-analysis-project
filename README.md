# Uber Data Analysis

## Project Overview
Analysis of Uber ride booking data from NCR region using PySpark to extract business insights on booking patterns, revenue, and vehicle performance.

## Dataset
- **Source**: `ncr_ride_bookings.csv` from [kaggle](https://www.kaggle.com/datasets/yashdevladdha/uber-ride-analytics-dashboard)
- **Records**: Uber ride bookings with booking status, customer details, vehicle types, payment methods, and ride metrics
- **Key Fields**: Booking Status, Vehicle Type, Payment Method, Booking Value, Ride Distance, Ratings

## Analysis Features

### 1. Booking Status Analysis
- Distribution of completed, incomplete, and cancelled rides
- Percentage breakdown of booking outcomes

### 2. Revenue Analysis
- Total revenue from completed rides
- Payment method performance (UPI, Debit Card, etc.)

### 3. Vehicle Performance
- Bookings by vehicle type (Sedan, Bike, Auto, eBike, etc.)
- Average ride distance and customer ratings per vehicle

### 4. Time Analysis
- Hourly booking patterns
- Peak demand hours identification

## Technologies
- PySpark (Data processing)
- Python (Analysis)
- Pandas (Visualization preparation)

## Key Code Features
```python
# Data loading with schema enforcement
df = spark.read.csv("static/ncr_ride_bookings.csv", header=True, schema=custom_schema)

# Analysis examples
booking_analysis = df.groupBy("Booking Status").agg(count("*").alias("count"))
revenue_by_payment = df.filter(col("Booking Status") == "Completed").groupBy("Payment Method")
```

## Getting Started
```bash
pip install pyspark pandas
python analysis.py
```

## Results
The analysis provides insights for optimizing Uber operations, improving service reliability, and increasing revenue through data-driven decisions.

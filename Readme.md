# Real-Time Transaction Monitoring System with AWS, PostgreSQL, and Grafana Cloud

This project leverages AWS services, PostgreSQL, and Grafana Cloud to create a real-time transaction monitoring system. The system generates synthetic banking transaction data using the Faker library and inserts the data into a PostgreSQL database hosted on AWS. The data is then connected to Grafana Cloud to visualize and monitor transactions in real time.

## Technologies Used

- **AWS** (Amazon Web Services) for hosting PostgreSQL database
- **PostgreSQL** as the database management system
- **Grafana Cloud** for real-time data visualization
- **Faker** library to generate synthetic transaction data
- **psycopg2** to connect Python to PostgreSQL
- **Pandas** for data manipulation and insertion into PostgreSQL
- **Python** for the backend and data generation

## Project Overview

The goal of this project is to simulate real-time banking transaction data and analyze it using Grafana dashboards. The key components include:

1. **Data Generation**: Using the `Faker` library, synthetic banking transaction records are generated and inserted into the PostgreSQL database.
2. **Data Storage**: The generated data is stored in an AWS-hosted PostgreSQL database.
3. **Data Visualization**: The PostgreSQL database is connected to Grafana Cloud, where real-time dashboards are created to monitor transaction data, identify trends, and visualize transaction patterns.

## Getting Started

## Prerequisites

To run this project, you will need:

- **AWS Account** with RDS (Relational Database Service) enabled.
- **PostgreSQL Database** set up on AWS.
- **Grafana Cloud** account for monitoring and dashboard creation.
- **Python 3.x** and required libraries installed.



## Setup

1. **Install Required Libraries**:
   You need to install the following Python libraries:
   ```bash
   pip install faker psycopg2 pandas


## Project Setup

## 1. Create the PostgreSQL Database on AWS

Follow these steps to create a PostgreSQL database on AWS:

1. **Log in to your AWS account.**
2. **Create an RDS instance** with PostgreSQL as the engine.
3. Ensure that the database is **publicly accessible**.
4. **Note down the connection details**, which will include:
   - Host
   - Port
   - Database name (dbname)
   - User
   - Password

## 2. Configure the Python Script

1. Download or clone the Python script provided in the project.
2. Replace the following connection details in the script with your **AWS RDS PostgreSQL** credentials:
   - `host`
   - `port`
   - `dbname`
   - `user`
   - `password`
   
## 3. Run the Script

The script will generate random transaction data and insert it into the PostgreSQL database at regular intervals (every 15 seconds in this case).

To run the script, use:

```bash
python app.py



## Real-Time Transaction Monitoring Dashboard in Grafana

This guide walks you through setting up a real-time dashboard in **Grafana** to visualize transaction data stored in **PostgreSQL**. It assumes that the data is being inserted into PostgreSQL at regular intervals and you want to visualize this data on Grafana.

## Prerequisites

Before you begin, make sure you have:

- A **Grafana Cloud** account.
- A **PostgreSQL database** with transaction data stored in it.
- The connection details for your PostgreSQL database (host, port, username, password).

## Steps

### 1. Connect PostgreSQL to Grafana Cloud

1. **Log in to your Grafana Cloud account.**

2. **Create a new data source**:
   - Navigate to **Configuration** > **Data Sources**.
   - Click on **Add data source** and select **PostgreSQL** as the data source.

3. **Provide PostgreSQL connection details**:
   - **Host**: Enter the host of your PostgreSQL database.
   - **Port**: Use the default PostgreSQL port (5432).
   - **Database name**: Enter your PostgreSQL database name.
   - **User**: Enter your PostgreSQL username.
   - **Password**: Enter your PostgreSQL password.

   Ensure that Grafana can connect to your PostgreSQL database. Test the connection after entering the credentials.

### 2. Create Dashboards in Grafana

Once your PostgreSQL data source is connected to Grafana, you can create dashboards to visualize the transaction data in real-time.

#### Some Useful Visualizations:

- **Total Transactions Per Minute**: 
   - Create a graph that shows the total number of transactions that occur each minute. You can use the `timestamp` field from your data and group it by minute.

- **Breakdown of Transactions by Merchant Category**: 
   - Create a pie chart or bar chart that breaks down the number of transactions by the merchant category (e.g., Retail, Electronics, Healthcare). Use the `merchant_category` field for this.

- **Trends in Transaction Amounts Over Time**: 
   - Create a time series graph to show the trend of transaction amounts over time. Use the `timestamp` and `amount` fields for this.

- **Detection of Potentially Fraudulent Activities**:
   - Create a panel that visualizes potentially fraudulent activities based on rules applied in the script. This could include transactions marked with specific fraud detection flags in the `rules_triggered` or `decision` fields.

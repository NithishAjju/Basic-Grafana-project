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

### Prerequisites

To run this project, you will need:

- **AWS Account** with RDS (Relational Database Service) enabled.
- **PostgreSQL Database** set up on AWS.
- **Grafana Cloud** account for monitoring and dashboard creation.
- **Python 3.x** and required libraries installed.

### Setup

1. **Install Required Libraries**:
   You need to install the following Python libraries:
   ```bash
   pip install faker psycopg2 pandas

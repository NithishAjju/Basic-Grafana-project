This project demonstrates the creation of a real-time monitoring dashboard for banking transactions using AWS, PostgreSQL, and Grafana Cloud. The system generates synthetic banking data using the Faker library, processes it using rules, stores it in a PostgreSQL database hosted on AWS, and visualizes it in Grafana Cloud.

Features
Synthetic Data Generation: Generates realistic banking transaction data using Faker, including attributes like merchant categories, card types, and transaction details.
Rules-Based Processing: Applies rules to the generated data to evaluate transaction decisions.
Database Integration: Stores transaction data in a PostgreSQL database hosted on AWS.
Real-Time Dashboards: Connects the database to Grafana Cloud to create real-time monitoring dashboards.
Prerequisites
Tools and Services
AWS: For hosting the PostgreSQL database.
PostgreSQL: Database for storing transaction data.
Grafana Cloud: For visualizing and monitoring real-time data.
Python: Script execution and data generation.
Faker Library: Generates synthetic data for transactions.
Python Libraries
Install the required Python libraries:

bash
Copy code
pip install psycopg2 Faker pandas
Project Structure
plaintext
Copy code
├── app.py               # Main script for data generation and insertion
├── requirements.txt     # Python dependencies
└── README.md            # Documentation
How It Works
Database Setup:

The PostgreSQL database is hosted on AWS RDS.
The banking_data table schema includes fields such as timestamp, transaction type, amount, card type, etc.
The script ensures the table is created if it does not already exist.
Data Generation:

The Faker library generates synthetic data, including:
Transaction types: Real_time_transaction, settlements, dispute.
Merchant categories: Retail, Electronics, Groceries, etc.
Card types: Visa, MasterCard.
Random transaction amounts and account details.
Data Insertion:

The generated data is processed, with rules applied to determine transaction decisions.
Data is inserted into the PostgreSQL database every 15 seconds.
Visualization with Grafana:

The PostgreSQL database is connected to Grafana Cloud.
Dashboards visualize key metrics such as transaction volume, flagged accounts, and category-specific trends.
Configuration
PostgreSQL Connection
Update the PostgreSQL connection details in the script:

python
Copy code
host = "your-aws-host"
port = 5432
dbname = "your-database-name"
user = "your-username"
password = "your-password"
Grafana Integration
Connect Grafana Cloud to your PostgreSQL database.
Configure panels and queries in Grafana to visualize the data.
Usage
Run the Script: Execute the Python script to start generating and inserting data:
bash
Copy code
python app.py
Monitor in Grafana:
Open Grafana Cloud and view the real-time dashboard.
Use preconfigured panels or create custom visualizations based on your requirements.
Customization
Modify the rules_triggered logic to implement custom business rules.
Adjust the data generation frequency by changing time.sleep(15).
Example Dashboard Metrics
Transaction Count by Type: Monitor the number of transactions (real-time, settlements, disputes).
Blacklisted Accounts: View the count of flagged accounts in real-time.
Top Merchant Categories: Identify popular transaction categories.
Transaction Volume: Track total and average transaction amounts over time.

# Project Nmae
STEDI Human Balance Analytics

# Project Idea
This project focuses on analyzing human balance data using AWS services. It involves ingesting data from landing zones,
transforming and filtering the data, and creating curated tables for analysis. The project utilizes AWS Glue, Amazon S3, and Amazon Athena to perform the required tasks.

# Project Structure
Project Structure
The project consists of the following files and directories:

customer_landing_to_trusted.py - Glue job script for ingesting and transforming customer landing zone data.
accelerometer_landing_to_trusted.py - Glue job script for ingesting and transforming accelerometer landing zone data.
step_trainer_trusted.py - Glue job script for ingesting and transforming step trainer landing zone data.
customer_landing.sql - SQL DDL script for creating the customer landing zone table.
accelerometer_landing.sql - SQL DDL script for creating the accelerometer landing zone table.
step_trainer_landing.sql - SQL DDL script for creating the step trainer landing zone table.
screenshots/ - A directory containing screenshots of various queries run on Athena.
README.md - This README file.

# Landing Zone
he landing zone is the initial storage location for the raw data. The project includes Glue jobs (customer_landing_to_trusted.py, accelerometer_landing_to_trusted.py, 
step_trainer_trusted.py) that connect to the S3 bucket for the customer, accelerometer, and step trainer landing zones. Make sure to configure the Glue jobs with 
the correct S3 paths and access permissions.

# Trusted zone
The trusted zone is where the transformed and filtered data resides. The Glue jobs (customer_landing_to_trusted.py, accelerometer_landing_to_trusted.py, step_trainer_trusted.py) 
are responsible for transforming the data and loading it into the trusted tables. The Glue job Python code should have the option to dynamically infer and update the schema enabled.

# Curated Zone
The curated zone contains the final curated tables for analysis. The Glue jobs (customer_trusted_to_curated.py, step_trainer_trusted.py, machine_learning_curated.py) 
perform the necessary joins and create the curated tables. The customer_trusted_to_curated.py Glue job should drop rows that do not have data in the sharedWithResearchAsOfDate column.cion

# Conclucion
The STEDI Human Balance Analytics project demonstrates how to ingest, transform, and analyze human balance data using AWS Glue, S3, and Athena. It provides insights into
the balance analytics process and showcases the use of AWS services for data engineering tasks.




# Real Estate Data Analysis & Azure Pipeline Project

![License](https://img.shields.io/badge/License-MIT-yellow.svg) ![Build](https://img.shields.io/badge/Build-Passing-brightgreen.svg)

## 🔍 Executive Summary

This project implements an end-to-end data analysis pipeline for real estate data, leveraging Microsoft Azure cloud services. It covers data ingestion from local sources to Azure SQL Database, data modeling using SSMS, transformation via Azure Data Factory dataflows, automated machine learning model training with Azure ML, and interactive visualization using Power BI. The goal is to extract actionable insights from real estate data through a robust and scalable cloud-based workflow.

## 📑 Table of Contents

1. [Project Objectives](#project-objectives)
2. [Workflow Overview](#workflow-overview)
3. [Dataset Overview](#dataset-overview)
4. [Technologies & Tools](#technologies--tools)
5. [Project Structure](#project-structure)
6. [Setup Guide](#setup-guide)
7. [Usage Instructions](#usage-instructions)
8. [Team Roles](#team-roles)
9. [Support & Contact](#support--contact)
10. [License](#license)

## 🎯 Project Objectives

- **Establish a Cloud-Based Data Pipeline**: Implement a full data workflow using Azure services (SQL DB, ADF, ML).
- **Data Ingestion & Modeling**: Securely upload local data to Azure SQL DB and define relationships using SSMS.
- **Data Transformation**: Clean, filter, and transform data using Azure Data Factory dataflows to create analysis-ready datasets.
- **Predictive Modeling**: Utilize Azure Automated ML to build and evaluate machine learning models based on the processed data.
- **Interactive Visualization**: Develop a Power BI dashboard connected to Azure SQL DB for insightful data exploration and reporting.
- **Provide Actionable Insights**: Deliver data-driven findings relevant to the real estate domain.

## 📊 Workflow Overview

The project follows these key steps:

1. **Infrastructure Setup**: Provision Azure Server and Azure SQL Database.
2. **Data Ingestion**: Upload local data to Azure SQL DB via a Python script.
3. **Database Modeling (SSMS)**: Design ERD and establish table relationships.
4. **Data Transformation (Azure Data Factory)**:
   - Ingest data from Azure SQL DB
   - Apply filters and transformations using ADF Dataflows
   - Generate a new, processed table
5. **Store Processed Data**: Save the transformed table back to Azure SQL Database.
6. **Machine Learning (Azure ML)**:
   - Connect Azure ML to the processed data in Azure SQL DB
   - Configure and run an Automated ML pipeline
7. **Data Visualization (Power BI)**:
   - Connect Power BI to the data in Azure SQL DB
   - Create an interactive dashboard

[Workflow Diagram showing: Source → Azure SQL Database → Azure Data Factory → Azure ML → Power BI → Visualization]

## 📁 Dataset Overview

- **Source**: Primarily local CSV files (Agents, Clients, Properties, Sales, Visits) ingested into Azure SQL DB
- **Domain**: Real Estate
- **Primary Attributes (examples - adapt based on actual data)**:
  - Property Details: Location, size, price, type
  - Sales Data: Transaction dates, prices, agent involved
  - Client/Agent Info: Contact details, preferences
  - Visit Data: Property visit logs, dates, feedback

## 🛠️ Technologies & Tools

**Functionality/Tools**

**Cloud Platform**: Microsoft Azure

**Database**: Azure SQL Database, SQL Server Management Studio (SSMS)

**Data Integration & Azure Data Factory (Dataflows)**: ETL

**Machine Learning**: Azure Machine Learning (Automated ML), Python (Scikit-learn, Pandas)

**Business Power BI Intelligence**

**Scripting & Data**: Python (Pandas, Pyodbc or similar) Handling

**Version Control**: Git, GitHub

## 📂 Project Structure

The repository is organized as follows:
├── config/ # Configuration files (e.g., config.json)
├── data/
│ ├── raw/ # Original raw input data (CSV files)
├── docs/ # Documentation (presentation.pdf, info.txt, etc.)
├── models/ # Trained ML models (model.pkl, MLmodel artifacts)
├── reports/
│ ├── dashboards/ # Power BI dashboards (dashboard.pbix)
│ ├── figures/ # Images and diagrams (ERD.jpg, ML_pipeline.jpg)
│ └── performance/ # Model performance data (TSV files)
├── scripts/
│ ├── dataflow/ # Azure Data Factory related scripts/configs/exports
│ ├── etl/ # SQL scripts (ERD.sql, table_queries.sql)
│ └── import.py # Python script for data ingestion to Azure SQL DB
├── models/ # Specifies intentionally untracked files
├── conda.yaml # Conda environment file (if used)
├── python_env.yaml # Python environment file (if used)
├── requirements.txt # Pip requirements file
└── README.md # This file



## ⚙️ Setup Guide

1. **Clone the Repository**:
   ```bash
   git clone <https://github.com/SayedELMASRY2/Real-Estate-analysis.git>
   cd <repository-name>
   Azure Setup:

Ensure you have an active Azure subscription
Provision the necessary resources: Azure SQL Database, Azure Data Factory, Azure Machine Learning workspace
Configure firewall rules and access permissions as needed
Configuration:

Update connection strings and other parameters in config/config.json and relevant scripts (src/import.py, ADF linked services, etc.) to match your Azure environment
Environment Setup:

Install required Python packages 
pip install -r requirements.txt
Usage Instructions
Data Ingestion: Run the Python script to upload data to Azure SQL DB:
python src/import.py
Data Transformation: Trigger the appropriate pipeline/dataflow within your Azure Data Factory instance
Machine Learning: Navigate to your Azure ML workspace, locate the Automated ML experiment/pipeline, and run it
Visualization: Open the dashboard.pbix file located in reports/dashboards/ using Power BI Desktop. Refresh the data connection to point to your Azure SQL Database

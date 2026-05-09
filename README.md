![Architecture Cover](diagrams/portada.png)

# Azure Medallion Data Pipeline

End-to-end Data Engineering project using Azure Data Factory, Azure Blob Storage, Databricks, PySpark and Delta Lake, implementing a Medallion Architecture approach.

## Project Overview

This project was developed as a final project for a Data Engineering program.  
The goal was to design and implement a complete data pipeline capable of ingesting, transforming, validating and analyzing construction material consumption data.

The solution simulates a real-world data engineering workflow using cloud services and layered data processing.

## Technologies Used

- Azure Data Factory
- Azure Blob Storage
- Azure Databricks
- PySpark
- Delta Lake
- SQL Database
- GitHub

## Architecture

The pipeline follows the Medallion Architecture pattern:

```text
Raw Data Sources
      ↓
Azure Data Factory
      ↓
Azure Blob Storage - RAW
      ↓
Databricks / PySpark
      ↓
Bronze Layer
      ↓
Silver Layer
      ↓
Gold Layer
      ↓
Analytical Outputs

Data Sources

The project uses different data sources:

CSV file with material consumption records
JSON file with construction material catalog
SQL table with supplier information

Due to GitHub file size limits, the repository includes a reduced sample dataset.
The original dataset used in the project contained approximately 500,000 records.

Medallion Layers
Bronze Layer

The Bronze layer stores raw ingested data in Delta format, preserving the original structure as much as possible.

Main tasks:

Read data from RAW storage
Load CSV, JSON and SQL-based datasets
Store data as Delta tables
Organize data for further processing
Silver Layer

The Silver layer applies cleaning, validation and enrichment logic.

Main tasks:

Remove duplicated records
Validate required fields
Filter invalid values
Standardize data types
Join consumption data with materials and suppliers
Calculate total material cost
Gold Layer

The Gold layer contains aggregated datasets ready for analysis and reporting.

Main outputs:

Total material cost by project
Top suppliers by historical spending
Top materials by consumption and cost
Business-ready analytical tables
Pipeline Flow
Data is ingested using Azure Data Factory.
Files are copied into Azure Blob Storage.
Databricks notebooks process the data.
Data is transformed through Bronze, Silver and Gold layers.
Final analytical tables are generated in Delta format.
The workflow is automated using scheduled triggers.
Repository Structure
.
├── datasets
│   └── Sample datasets used for the project
├── diagrams
│   └── Architecture and pipeline diagrams
├── docs
│   └── Final project documentation
├── notebooks
│   ├── bronze
│   ├── silver
│   └── gold
└── README.md
Business Context

The dataset represents material consumption in construction projects.
The pipeline allows the analysis of costs, suppliers and materials across different projects, supporting better decision-making in construction management.

This project combines construction industry knowledge with data engineering practices.

Security Notes

Sensitive information such as passwords, tokens, access keys and connection strings was removed from this public repository.

Author

Walter Lopez
Architect | Data Analytics | Data Engineering


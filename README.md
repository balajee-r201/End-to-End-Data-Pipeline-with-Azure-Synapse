# Azure-Synapse---Serverless-Pool-Project
## Overview
This project leverages **Azure Synapse Serverless Pool** for data ingestion and transformation. The dataset used in this project comes from the **National Renewable Energy Laboratory (NREL)** and focuses on **electric charging station locations** across the U.S.

## Dataset
- **Source:** [Alternative Fueling Station Locator API](https://developer.nrel.gov/docs/transportation/alt-fuel-stations-v1/)
- **Format:** JSON
- **Description:** The dataset includes station locations for **biodiesel, compressed natural gas, ethanol, electric charging, hydrogen, liquefied natural gas, and propane.** However, only **electric charging stations** were filtered for analysis.

## Challenges Faced
1. **Configuring the REST API linked service** to copy JSON data into **Azure Data Lake Storage (ADLS)**.
2. **Handling large JSON files**, as the dataset required extensive parsing and transformation.

## Solutions & Actions Taken
- Followed **YouTube tutorials** to set up the **REST API linked service** in Azure.
- Used **trial and error** to resolve JSON parsing issues.

## Data Ingestion Pipeline
### **Step 1: API to JSON in ADLS**
- Used **Copy Activity** in **Azure Data Factory (ADF)** to store API data in **ADLS Gen2**.
- Configured a **REST API linked service** as the data source.

#### **Configuration Details**
- **Base URL:** `https://developer.nrel.gov/api/alt-fuel-stations/v1.json?fuel_type_code=ELEC&api_key=<API_KEY>`
- **Authentication Type:** Anonymous
- **Output Format:** JSON file stored in ADLS

## Next Steps
- Implement **data transformation** and **query optimization** using **Azure Synapse SQL Pool**.
- Integrate with **Power BI** for visualization.
- Automate data pipeline using **Azure Data Factory triggers**.
## Architecture Diagram
Below is the architecture for this project, showing the data flow from API to Power BI:

---

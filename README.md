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
![Arch](https://github.com/user-attachments/assets/cb62a031-0e16-4db1-b88f-dc75f67102f6)
## Power BI Dashboard
<img width="667" alt="Power BI Dashbord" src="https://github.com/user-attachments/assets/8219dc54-3041-437b-911a-5f2c26b94f93" />

## Pipeline
<img width="800" alt="Pipeline" src="https://github.com/user-attachments/assets/48de3f80-913c-441c-ae6e-7603a802a395" />

I have designed a dummy pipeline to automate the entire orchestration, and I’m excited to take it to the next level! 🚀 There’s plenty of opportunity for improvement, and I’m actively working on enhancing it with scheduled and event-based triggers to achieve full automation—from data ingestion to dynamic Power BI dashboards. 

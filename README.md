# DSC202_final_project

## Title: Joint Databases for Electronic Health Record Analysis
Group Members: Teresa Lee, Tino Trangia, Micah Hunter

### Video Presentation about our project:
https://drive.google.com/file/d/15b9CFIhlCw2wgkapxL_2Qp4AD6Ne-dhQ/view?usp=sharing

## Data Sources
1. Synthetic patient medical records (i.e. Electronic Health Records or EHRs) from [Synthea](https://synthea.mitre.org/downloads/). We used both the 1000 Sample and 100 Sample CSV files. Data dictionary and in-depth information about the various CSV files can be found on the [FHIR website](https://build.fhir.org/resourcelist.html). For example, the attributes for each patient are describe [here](https://build.fhir.org/patient.html). We have included CSVs for patients and conditions, as well as their SQL schemas, in the **data** directory. 
2. Social Determinants of Health (SDOH) from Agency for Healthcare Research and Quality (AHRQ) found [here](https://www.ahrq.gov/sdoh/data-analytics/sdoh-data.html). Originally available as .xlsx but we have converted to CSV for our project. We used the 2020 Zip Code based data. The codebook is included in our **data** directory. Preprocessing steps, such as filtering relevant columns and records (and Neo4j import), are included in the **data_preprocessing** directory. 

## Project Setup Instructions
You can use [Neo4j Sandbox](https://neo4j.com/sandbox/), a cloud-based, short-term instance of Neo4j database that is good for quick projects and exploring graph DB without local setup. You can also use a desktop installation of Neo4j and modify the driver details accordingly. See documentation [on the Neo4j site](https://neo4j.com/docs/python-manual/current/) for using Neo4j with Python. We also used PostgreSQL with Datagrip for relational data.

Steps for replicating this project:
1. Clone the repo
2. Download the [Synthea data](https://synthea.mitre.org/downloads/). We used the 100 Sample Synthetic Patient Records, CSV.
3. Create a directory called 'csv' in your local repo and unzip the Synthea data (all .csv files) into it.
4. Edit main.ipynb with the correct driver information (see sandbox tab -> connect via drivers -> Python).
5. Run the cells in main.ipynb, which will read the CSV data and merge it into the sandbox database.
6. Download the [SDOH data (ZIP code)](https://www.ahrq.gov/sdoh/data-analytics/sdoh-data.html) from AHRQ. Place **SDOH_2020_ZIPCODE_1_0.xlsx** into your local repo.
7. Run sdoh.ipynb (in the **data_preprocessing** directory). This will read in the excel data into a Pandas dataframe, then filter for rows corresponding to Massachusetts zip codes (as all the synthetic patient records are from Massachusetts). It then write the data to a CSV file in the main directory. It will import the nodes to the Neo4j instance, and the CSV can be further processed and used with PostgreSQL. For example, you can move **sdoh_ma.csv** into the **data_preprocessing** directory and run **filter_zipcode_citizenship_data.ipynb** to filter for desired columns and then import into PostgreSQL using our provided schema. 
8. Now you can start querying the data. See the **query_examples** directory for the queries we used in the presentation. You can simply copy-paste SQL queries to the Datagrip terminal and Cypher queries to the Neo4j browser.

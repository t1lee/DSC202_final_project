# DSC202_final_project

## Title: Joint Databases for Electronic Health Record Analysis
Group Members: Teresa Lee, Tino Trangia, Micah Hunter

### Video Presentation about our project:
https://drive.google.com/file/d/15b9CFIhlCw2wgkapxL_2Qp4AD6Ne-dhQ/view?usp=sharing

## Data Sources
1. Synthetic patient medical records (i.e. Electronic Health Records or EHRs) from [Synthea](https://synthea.mitre.org/downloads/). We used both the 1000 Sample and 100 Sample CSV files. Data dictionary and in-depth information about the various CSV files can be found on the [FHIR website](https://build.fhir.org/resourcelist.html). For example, the attributes for each patient are describe [here](https://build.fhir.org/patient.html). We have included sample files in the **data** directory.
2. Social Determinants of Health (SDOH) from Agency for Healthcare Research and Quality (AHRQ) found [here](https://www.ahrq.gov/sdoh/data-analytics/sdoh-data.html). Originally available as .xlsx but we have converted to CSV for our project. We used the 2020 Zip Code based data. This data is also included in our **data** directory.

## Neo4j Sandbox setup
[Neo4j Sandbox](https://neo4j.com/sandbox/) is a cloud-based, short-term instance of Neo4j database that is good for quick projects and exploring graph DB without local setup. 
Steps for replicating this project:
1. Clone the repo
2. Download the [Synthea data](https://synthea.mitre.org/downloads/). We used the 100 Sample Synthetic Patient Records, CSV.
3. Create a directory called 'csv' in your local repo and unzip the Synthea data in it.
4. Edit main.ipynb with the correct driver information (see sandbox tab -> connect via drivers -> Python).
5. Run main.ipynb, which will read the CSV data and merge it into the sandbox database.

# DSC202_final_project

### Title: Social Determinants of Health (SDOH), Survey Data, and Network Analysis
Group Members: Teresa Lee, Tino Trangia, Micah Hunter

## Neo4j Sandbox setup
[Neo4j Sandbox](https://neo4j.com/sandbox/) is a cloud-based, short-term instance of Neo4j database that is good for quick projects and exploring graph DB without local setup. 
Steps for replicating this project:
1. Clone the repo
2. Download the [Synthea data](https://synthea.mitre.org/downloads/). We used the 1K Sample Synthetic Patient Records, CSV.
3. Create a directory called 'csv' in your local repo and unzip the Synthea data in it.
4. Edit main.ipynb with the correct driver information (see sandbox tab -> connect via drivers -> Python).
5. Run main.ipynb, which will read the CSV data and merge it into the sandbox database.

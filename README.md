# Chicago Crime

The repository covers a project aimed to analyze Chicago crime data in relation to socioeconomic factors to provide actionable insights and recommendations for reducing crime rates through effective data visualization and trend analysis.

### Project Objective: 

Chicago has been identified as a city with one of the highest crime rates in the United States. Crime rates can impact tourism, immigration, and business opportunities while also providing a measurement for how policy reform has impacted a city. This project will analyze crime trends over the past 20 years in Chicago, looking at the correlation between geography, income, and crime, and how policy has impacted crime rates, crime types, and citizen sentiment related to safety and trust of the police.

### Methodology:

1. Identification of datasets
  -   Reported incidents of crime that occurred in the City of Chicago from 2001 to present
  -   Data is extracted from the Chicago Police Department's CLEAR (Citizen Law Enforcement Analysis and Reporting) system
  -   Survey of citizen safety and police sentiment scores 
2. Development of relational models
  - Data preprocessing to select only relevant columns to analysis
  - Determined Primary Keys and Foreign Keys to create relationships between tables
3. Extraction/Cleaning of data
  - Download of data into CSV format
  - Development of python script to clean/import records into relational models
  - Import of records into relational model developed by team via Google Cloud
4. Development of visualizations
  - Development of data source modeling based on ETL tables
  - Visualizations developed to address questions raised in business case
  - Inclusion of filtering based on time to review time series trends

# Overview: 

**1. Data**

https://data.cityofchicago.org/browse?category=Public%20Safety

https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2

https://data.cityofchicago.org/Public-Safety/Police-Sentiment-Scores/28me-84fj

**2. Data Preprocessing**

*Files in repository: ETL Script, PythonGCP Script, Data Model MySQL Workbench Model, STM Sheet*

<ins>Database and Tools:</ins> 

- MySQL Workbench to create relational model and EER diagram
- Google Sheets for Source to Target Mapping (STM)
- Python to clean and transform data and load into Google Cloud Storage
- Google Cloud Storage to store cleaned dataset
- Google BigQuery to query dataset
  -  Cloud Storage and BigQuery were utilized due to the size of the dataset being large enough to cause issues within SQL Server
- Tableau to create reports and dashboard

<ins>Data Modeling:</ins>

A normalized, relational diagram was created as there were not enough tables to necessitate a dimensional model. We did not require denormalization in any of our tables.

- Assume that District ID in both datasets match
- Rows containing columns that are NULL will be dropped such as: IUCR, FBI, Beat, etc. 

<img width="832" alt="team3_eer_diagram_final" src="https://github.com/user-attachments/assets/f14099b6-9a3a-4e0a-850a-925db2c9ef45">

<ins>Aggregations Performed:</ins>

- Average of Safety Grouped by District
- Average of Trust Grouped by District
- Average of Safety Grouped by District For Low, Medium and High Income Levels Respectively
- Average of Trust Grouped by District For Low, Medium and High Income Levels Respectively 



**3. Visualization**


<img width="1440" alt="Screenshot 2024-10-18 at 6 14 10 PM" src="https://github.com/user-attachments/assets/417d34b9-793b-49d9-a7e1-55ce44968ddf">

<img width="1440" alt="Screenshot 2024-10-18 at 6 14 18 PM" src="https://github.com/user-attachments/assets/a871164a-e60e-4cd0-b347-91f709c06bc9">

<img width="1440" alt="Screenshot 2024-10-18 at 6 15 00 PM" src="https://github.com/user-attachments/assets/a6b2435a-6405-4cf0-b432-488c4d5adf9d">

<img width="1440" alt="Screenshot 2024-10-18 at 6 15 06 PM" src="https://github.com/user-attachments/assets/522796c9-e28f-401a-a9be-961f4b75ded5">

<img width="1440" alt="Screenshot 2024-10-18 at 6 15 13 PM" src="https://github.com/user-attachments/assets/23f5f72b-9bfc-4be3-a91b-da82e8503d8d">

<img width="1440" alt="Screenshot 2024-10-18 at 6 15 20 PM" src="https://github.com/user-attachments/assets/58932066-ad37-4c98-bed7-22ed7ac8d5ac">

<img width="1440" alt="Screenshot 2024-10-18 at 6 15 27 PM" src="https://github.com/user-attachments/assets/e50555fd-c13b-4873-beb7-bec86e3388b8">

<img width="1440" alt="Screenshot 2024-10-18 at 6 15 34 PM" src="https://github.com/user-attachments/assets/3f6ced4c-f13b-49f7-b559-5e2beeac9992">

<img width="1440" alt="Screenshot 2024-10-18 at 6 15 40 PM" src="https://github.com/user-attachments/assets/935e4800-3aa5-450b-8dab-ddb5e2388372">

**4. Insights and Recommendations**

- More resources allocated to theft, battery and criminal damages
- Overall positive correlation between safety and trust sentiment scores
  - More resources to build trust in areas with low sentiment scores of safety and trust
    - District 7  - Englewood South side
    - District 11 - Harrison (West Garfield)
- Deeper analysis into Englewood -  Highest crime per capita and lowest safety and trust sentiment scores
- Further analysis to determine if high trust causes low crime or vice-versa

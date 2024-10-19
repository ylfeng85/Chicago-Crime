# Chicago Crime

The repository covers a project aimed to analyze Chicago crime data in relation to socioeconomic factors to provide actionable insights and recommendations for reducing crime rates through effective data visualization and trend analysis.

### Project Objective: 

Chicago has been identified as a city with one of the highest crime rates in the United States. Crime rates can impact tourism, immigration, and business opportunities while also providing a measurement for how policy reform has impacted a city. This project will analyze crime trends over the past 20 years in Chicago, looking at the correlation between geography, income, and crime, and how policy has impacted crime rates, crime types, and citizen sentiment related to safety and trust of the police.

## Objectives:

1. City of Chicago wants better understanding of crime rates and police sentiment across the city analyzed over time
    - Prevalence of crime in different neighborhoods
    - Types of crimes being committed
    - How crimes influence citizens’ feeling of safety and trust in police
2. City officials want to identify heavily impacted areas
    - Determine if areas need additional reforms
    - Do areas need reform changes to make a higher impact
3. Analysis will include
    - Distribution of crime by type
    - Distribution of crime by region
    - Citizen sentiment by region and income


## Repository Structure

**Data Model** (Chicago_Crime_data_model.mwb)

- Contains the MySQL Workbench file to create relational model and EER diagram

**STM** (STM.xlsx)
- Contains the Google Sheets for Source to Target Mapping (STM)

**Google Cloud Storage Loading** (Chicago Crime Database ETL.html, ETL Script.ipynb)
- Contains a Python notebook to clean and transforma data to load into Google Cloud Storage for data storage

## Methodology:

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

## Data

https://data.cityofchicago.org/browse?category=Public%20Safety

https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2

https://data.cityofchicago.org/Public-Safety/Police-Sentiment-Scores/28me-84fj

## Data Preprocessing

### Database and Tools:

- MySQL Workbench to create relational model and EER diagram
- Google Sheets for Source to Target Mapping (STM)
- Python to clean and transform data and load into Google Cloud Storage
- Google Cloud Storage to store cleaned dataset
- Google BigQuery to query dataset
  -  Cloud Storage and BigQuery were utilized due to the size of the dataset being large enough to cause issues within SQL Server
- Tableau to create reports and dashboard

### Data Modeling:

A normalized, relational diagram was created as there were not enough tables to necessitate a dimensional model. We did not require denormalization in any of our tables.

- Assume that District ID in both datasets match
- Rows containing columns that are NULL will be dropped such as: IUCR, FBI, Beat, etc. 

<img width="832" alt="team3_eer_diagram_final" src="https://github.com/user-attachments/assets/f14099b6-9a3a-4e0a-850a-925db2c9ef45">

### Aggregations Performed:

- Average of Safety Grouped by District
- Average of Trust Grouped by District
- Average of Safety Grouped by District For Low, Medium and High Income Levels Respectively
- Average of Trust Grouped by District For Low, Medium and High Income Levels Respectively 



## Key Questions, Insights and Visualizations

### 1. Is there a pattern of amount of crime over time?

Analysis: We analyzed the trend of crime incidents over time.

Visualization: Line plot illustrating crime counts by year.

Insight: Our data shows overall crime decreasing over time.

<img width="1440" alt="Screenshot 2024-10-18 at 6 14 10 PM" src="https://github.com/user-attachments/assets/417d34b9-793b-49d9-a7e1-55ce44968ddf">

### 2. Did the most common type of crime remain consistent throughout the years?

Analysis: We evaluated count of crime over a decade, separated into the first half and last half of the decade (5 years each).

Visualization: Heatmat of crime type by year.

Insight: Theft, Battery & Criminal Damage remain top three crime types across the last ten years.

<img width="1440" alt="Screenshot 2024-10-18 at 6 14 18 PM" src="https://github.com/user-attachments/assets/a871164a-e60e-4cd0-b347-91f709c06bc9">

### 3. What districts of Chicago had the highest amount of crime per capita? 

Analysis: We assessed crime rates per capita across different neighborhoods.

Visualization: Heatmap depicting crime per capita by neighborhood.

Insight: Englewood, East Garfield Park and West Englewood have the highest crime per capita in Chicago.

<img width="1440" alt="Screenshot 2024-10-18 at 6 15 00 PM" src="https://github.com/user-attachments/assets/a6b2435a-6405-4cf0-b432-488c4d5adf9d">

### 4. Did the most common type of crime remain consistent throughout the years?

Analysis: We visualized the correlation between trust scores of citizens and safety scores of neighborhoods.

Visualization: Scatterplot of overall trust plotted against overall safety.

Insight: There is a strong positive correlation between overall safety scores and trust.

<img width="1440" alt="Screenshot 2024-10-18 at 6 15 06 PM" src="https://github.com/user-attachments/assets/522796c9-e28f-401a-a9be-961f4b75ded5">

### 5. Is there a correlation between income levels and safety scores?

Analysis: We examined the relationship between low, medium, and high income levels and their corresponding safety scores.

Visualization: Three scatterplots showing each income level plotted against overall safety scores.

Insight: High income residents trust police in their districts despite safety scores.

<img width="1440" alt="Screenshot 2024-10-18 at 6 15 13 PM" src="https://github.com/user-attachments/assets/23f5f72b-9bfc-4be3-a91b-da82e8503d8d">

<img width="1440" alt="Screenshot 2024-10-18 at 6 15 20 PM" src="https://github.com/user-attachments/assets/58932066-ad37-4c98-bed7-22ed7ac8d5ac">

<img width="1440" alt="Screenshot 2024-10-18 at 6 15 27 PM" src="https://github.com/user-attachments/assets/e50555fd-c13b-4873-beb7-bec86e3388b8">

### 6. Which districts have the lowest overall Safety and Trust scores?

Analysis: We assessed safety and trust scores across various districts in Chicago.

Visualization: HHeatmap displaying overall safety and trust scores by district.

Insight: Overall Safety and Trust scores are the lowest for Englewood and Harrison.

<img width="1440" alt="Screenshot 2024-10-18 at 6 15 34 PM" src="https://github.com/user-attachments/assets/3f6ced4c-f13b-49f7-b559-5e2beeac9992">

### 7. Is there a difference in correlation between trust and safety scores for each income level group? 

Analysis: We examined the relationship between trust and safety scores within different income level groups.

Visualization:  Scatterplot illustrating the correlation between trust and safety scores by income segments, along with a correlation matrix for trust and safety ratings.

Insight: There is overall a positive correlation between safety and trust sentiment scores. However, low and medium-income residents tend to trust the police when safety scores are high. In contrast, there is a weaker correlation for high-income residents, who maintain trust in the police even when safety scores are low.

<img width="1440" alt="Screenshot 2024-10-18 at 6 15 40 PM" src="https://github.com/user-attachments/assets/935e4800-3aa5-450b-8dab-ddb5e2388372">


## Conclusion and Recommendations

Based on the insights from this analysis

**1. Allocate More Resources to Specific Crimes:** Increase resources dedicated to addressing theft, battery, and criminal damage to enhance community safety.

**2. Leverage the Positive Correlation Between Safety and Trust:** Focus on building trust in areas with low safety and trust sentiment scores to improve overall community sentiment.

**3. Target Districts:**
  - District 7 - Englewood (South Side)
  - District 11 - Harrison (West Garfield)
    
**4. Conduct a Deeper Analysis of Englewood:** Investigate Englewood further, as it exhibits the highest crime rate per capita along with the lowest safety and trust sentiment scores.
    
**5. Explore the Relationship Between Trust and Crime:** Analyze whether higher trust levels lead to lower crime rates or if low crime rates foster higher trust in the police.

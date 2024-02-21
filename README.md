# PokémonGoPvP
Pokémon Go PvP Master League Encounter Prediction Model
Data cleaning logs
-data acquired from pvpoke.com on feb 18!
2/18/2024 15:26:00 Cleaning and Analyzing data with SQL

Uploading dataset csv uploaded cp10000_all_overall_rankings on SQL dataset ‘pokemon’
Creating a new table in SQL ml100_casestudy
Writing queries to clean and organize
SELECT *
FROM `coursera-411817.pokemon.ml100_casestudy`
   ORDER BY(Score) DESC
   LIMIT(101)
#here top 100 ml pvp pokemon have a 
Score >= 75.2


Storing this new data in a new table ml_top100_casestudy



 Cleaning ml_top100_casestudy dataset 
Grouping by Type_1
Ordering by number of Type_1 DESC
SELECT
 Type_1, COUNT(Type_1) AS Num_Type_1
FROM `coursera-411817.pokemon.ml_top100_casestudy`
WHERE Score >= 75.2
    GROUP BY Type_1
     ORDER BY Num_Type_1 DESC

 Storing new data in new table in SQL `ml_top_100types_casestudy`
# there are 16 different Pokémon types in the top 100


Now sorting the top 10 by limiting Pokemon top groups 
SELECT
 Type_1, COUNT(Type_1) AS Num_Type_1
FROM `coursera-411817.pokemon.ml_top100_casestudy`
WHERE Score >= 75.2
    GROUP BY Type_1
     ORDER BY Num_Type_1 DESC
     LIMIT 10
			 
 Store the new dataset as new csv
`ml_top10_types_casestudy.csv` 
And download this table as .CSV file


Also download the 
`ml_top100_types_casestudy.csv` 

# For data visualizations
  All files stored in map Desktop>CASE_STUDY>CASESTUDY_Masterleague>pvpdata

2/18/2024 16:04:31 Data analysis and data visualization with 
Google spreadsheets 	


Importing data in google spreadsheets 
Import `ml_top10_type_casestudy.csv`
Clean data and make charts
ml_top10_types_casestudy_table_V2,
# ml_top10_types_casestudy_table_V2 is a table chart
				# All tables stored on desktop file CASE_STUDY>CASESTUDY_Masterleague>images_casestudy>charts



2/18/2024 16:32:30
			Data visualization with Tableau

Importing dataset `ml_top10_types_casestudy`
Importing dataset `ml_top100_types_casestudy`

Creating bubble chart and horizontal bar chart



2/18/2024 17:00
Creating new dataset in Google Spreadsheets
Adding and converting encounter numbers into encounter rate percentage
Designing new table chart with Pokemon type, Number of encounters, and Encounter rate percentage
Downloading table chart and uploading on presentation
File names: `Number_per_type and Encounter_rate.png`
`ml_top10_types_casestudy_V2`



2/18/2024 17:30

Data Visualization with Tableau
Uploaded dataset `ml_to10_types_casestudy_V2`
Design horizontal barchart
Design barchart
Design bubble chart


2/18/2024 18:00
Case study presentation with Google Slides
Download, store and upload images on slides
Upload created charts on Google Slides

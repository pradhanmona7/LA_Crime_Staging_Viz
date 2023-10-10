# LA_Crime_Staging_Viz
Data Warehouse-Data Visualization-Data Cleaning-MySQL-Azure Data Studio-Talend-Altreyx

**Tools Used: 
Data Profiling: Altreyx
Data Cleaning: Talend
ETL tool: Talend
Data Visualization: PowerBi and Tableau**

**About LA Crime Data**
This dataset provides information on crime incidents in the City of Los Angeles dating back to 2020. 
The data is sourced from original crime reports that were transcribed from paper records, which may contain some inaccuracies.

**Data Profiling using Altreyx**
Data Investigation Tool: Basic Profile| Browse
Preparation Tool: Unique| Select
**Following are my views on LA Crime Data after profiling the data**
1.	All the records in DR_No column are unique which can be set to primary key with data type as Long/Bigint
2.	The Date_Rptd and Date_Occ has following date-time data type and the format of this columns are MM-DD-YYYY HH:MM:SS.
3.	The Area Code with 12 and Area Name with 77th Street has the highest crime rate with 26368 crime happened that is around 6.45% of total crime
4.	The column Part1-2 has 239220 (58.52%) records under part 1 and rest under part 2
5.	From Crm Cd Desc we see that Vehicle stolen has the highest crime rate with 10.87% of total crime reported
6.	The Vict Age column in the dataset displays some noticeable irregularities. Firstly, it contains numerous outliers, which are data points that significantly differ from the usual age range. Additionally, a sizable portion of the dataset, comprising approximately 98,709 entries, contains the value zero, indicating the absence of age information for these cases. Furthermore, it's important to highlight that the column includes negative values such as -1, -2, -3 which lack practical relevance when interpreting age-related data. This emphasizes the importance of assessing data quality and considering potential data cleaning measures to ensure the accuracy and meaningfulness of age-related information within the
7.	Analyzing the Victim Sex column reveals that 42.27% of the cases are male, followed by 36.51% that are female, 13% containing null values and 8.03% unknown values. There are some values represented by H which is not clear to us so that column can be imputed to X.
8.	The Weapon with Code 400 and Description Strong Arm (Hands, Fist, Feet or Body) is the highest used one. 
9.	Around 3,15,268 cases out of 408718 cases have been resolved, or the investigations have been concluded which is around 77% of total crime reported.
**Basic Data Profiling using Altreyx**
1.	Using the Basic Profile, I decided the data types of each column
2.	Further Basic Profile was used to calculate the length of each column depending on the longest length of the column
3.	Identify Unique columns/ duplicates
4.	Used Formula in Altreyx to transform the inconsistent date to a standard value
Following is the screen shot of Altreyx workflow:

<img width="468" alt="image" src="https://github.com/pradhanmona7/LA_Crime_Staging_Viz/assets/114325852/eee6118c-fb3a-4f4a-9134-efea56053ee8">


**Data Cleaning using Talend Studio**
•	From the Basic Profile, We can see that the age has some values like 0,-1,-2,-3 that are not practically possible. So I used Mean/Median/Mode Imputation toCalculate the mean, median, or mode of a column and replace missing values with these statistics. You can use Talend's aggregation functions in combination with the tAggregateRow component.
•	For Missing values I cleansed the data by Constant value imputation the tMap component to replace missing values with a constant value.

**ETL Using Talend Studio**
Using Talend Extracted the data from CSV file tranformed the data and loaded the data to Azure SQL Server and MySQL
Talend Workflow for ETL:

<img width="935" alt="Screenshot 2023-10-08 at 10 15 46 PM" src="https://github.com/pradhanmona7/LA_Crime_Staging_Viz/assets/114325852/9f8a37bc-9775-486a-82c1-5cd7ec076260">

**Data Visualization using PowerBi and Tableau**
Connected MySQL to Tableau
Connected Azure SQL Server to PowerBi
and created the visualization

Some Screenshots of Visualization:

![image](https://github.com/pradhanmona7/LA_Crime_Staging_Viz/assets/114325852/9305d647-7a25-4e6a-9399-1969ff1d6b9d)
![image](https://github.com/pradhanmona7/LA_Crime_Staging_Viz/assets/114325852/6c786708-5d84-4b2a-a1d9-fcd959d858a0)
![image](https://github.com/pradhanmona7/LA_Crime_Staging_Viz/assets/114325852/d3b973fc-dc97-4185-b63d-665068caf627)
![image](https://github.com/pradhanmona7/LA_Crime_Staging_Viz/assets/114325852/8c49e48e-303c-411d-8fa1-5ab95ed8b2d7)
![image](https://github.com/pradhanmona7/LA_Crime_Staging_Viz/assets/114325852/ddf97afe-2ac6-4b82-aeff-55277640d5c4)
![image](https://github.com/pradhanmona7/LA_Crime_Staging_Viz/assets/114325852/23e0b2b8-9b6b-4738-b7ed-4deeb6771e21)








# IMDb Analysis
![](https://github.com/MorganTheAnalyst/Movie_Data_Analysis/blob/master/Images/Theme.jpg)
## Overview:
The aim of the project was to analyze a movie dataset and explore various aspects such as movie genres,ratings, director popularity, and release year trends. Additionaly, an interactive dashboard was to be created using tools like Tableau and power Bi.

## Data Source:
I downloaded the data used in this project from Kaggle which consisted of all movies in the internet movies database (IMDb) from the year 1920 to 2020. The data had 16 columns and 999 rows. The columns were:
1. Poster_Link
2. Series_Title
3. Released_Year	
4. Certificate	
5. Runtime	
6. Genre	
7. IMDB_Rating	
8. Overview	
9. Meta_score	
10. Director	
11. Star1	
12. Star2	
13. Star3	
14. Star4	
15. No_of_Votes	
16. Gross

## Tools Used:
1. Python Libraries: Pandas, Matplotlib, Seaborn
2. Visualization Tool: Tableau

## Data Pre-Processing:
### a. Dropping Irrelevant Columns
I dropped Poster_Link and Overview columns which were not to be used for analysis in this particular project.

### b.  Handling Duplicates
The data did not have any duplicates.

### c. Handling data types
All the columns by default were objects so I had to convert the numeric columns to numeric data types. These columns were; <br>
(i). Runtime- int32 </br>
(ii). IMDB_Rating- float64 </br>
(iii). Meta_Score- float64 </br>
(iv). No_of_Votes- int64 </br>
(v). Gross- float64 </br>

### d. Addressing Inconsistent data
The only inconsistency that was to be addressed in the data was removing leading and trailling white spaces in non-numerical columns.

## Exploratory Data Analysis:
### 1. Genre  Analysis
Under genre analysis some of the aspects that were explored were; <br>
(i). The number of movie per Genre <br>
(ii). Average IMDb Rating per genre <br>
(iii). Number of votes per genre <br>
(iv). Total gross per genre <br>

### 2. Direcor Analysis:
(i). Top 10 Direcors by number of Movies <br>
(ii). Top 10 Direcors by Gross <br>
(iii). Top 10 direcors by rating <br>
(iv). Top 10 direcors by meta_score <br>
(v). Top 10 directors by runtime <br>

### 3. Star Analysis:
(i). Top 10 stars by Gross <br>
(ii). Top 10 stars by rating <br>
(iii). Combination of stars with the highest mean gross <br>
(iv). Combination of stars with the highest IMDb Rating <br>

### 4. Certificate Analysis:
### 5. Time Analysis:
(i). Movie release trend <br>
(ii). Average gross trend <br>
(iii). Rating trend <br>
(iv). Meta score trend <br>
(v). Number of votes trend <br>

### 6. More Analysis:
(i). Correlation  between numerical features.

## Challenges and Solutions:

### Challenge: 
Having rows with more than one genre under the "Genre" column.
### Solution:
I created a copy of the original dataframe(data2) and split genre column into separate rows depending on the different types of genres in that  row. eg "The Dark Knight" had 3 different genres ie Action, Crime and Drama hence I split that row into 3 different rows each with the respective genre.
### Reason:
The reason why I used this approach was to analyze the data effectively where analysis "by genre" was necessary by using the groupby() command.


### Challenge:
Having 4 different columns ie Star1, Star2, Star3, Star4.
### Solution:
I reolved the issue by using the melt() function in pandas to combine star column into a single column and saved the results into a new dataframe called data_melted.
### Reason:
This was done so as to perform "single star" analysis eg Top 10 stars by Gross.

## Dashboard Creation
![](https://github.com/MorganTheAnalyst/Movie_Data_Analysis/blob/master/Images/Dashboard_Screenshot.jpg)
I used Tableau as my visualization tool to create an interactive dashboard that a user can control based on their preference by use of filters created to enhance the interactivity. The dashboard has 3 main sections which are, the heading and filter section, the overview section which gives a quick summary and the visualization section which contains visuals like bar charts.

The data that was used in creation of the dashboard ("imdb_data_clean.csv"), is the data that was stored in data2 which was then saved as a csv file.
The reason why data2 was used is because of the resolved issue of the "Genre" column that was addressed under Challenges and Solutions section since it was in a format that was easy to use to create accurate visuals.

Two filters ie genre and year_released were created to enhance a user to filter the data based on preference and interests. For example, a user can filter data based on the movies that were released after the year 2019 under Crime and Drama genre. The dashboard was then saved in Tableau public where a user can access it for free.

# Capital Bike Data Exploration
## by Ibukun Irinyenikan

## Dataset

The data consists information regarding the characteristics of bike share riders.
The data collected is a total of 2.7 million ride records of bike riders from January to December, 2021.
The data is a total of 12 files. Each of the files are records of bike riders for each month of the year.
The dataset were collected through a link on Capitabikeshare website: https://s3.amazonaws.com/capitalbikeshare-data/index.html.
The dataset description can be found on Capitabikeshare website: https://ride.capitalbikeshare.com/system-data

#### Data Wrangling Process

##### Accessing And Cleaning Data 

After the dataset was visually and programmatically accessed, both quality and tidyness issues were spotted.
These  issues were fixed in a step by step process
The following highlights some of the quality issues that were fixed:

- Missing Data were fixed
- Incorrect Data type in the date columns were converted to datetime.
- Inappropriate column names were renamed to names that better describe the columns.
- Wrong data records were excluded from the dataset. 
    - Example of such records are data records with less than 1 minute trip duration 
    and records with less than 100 meter distance covered.

The tidyness issue that were fixed includes:
- Dropping columns that were not useful for analysis.
    - Example of such columns are the geographical data columns: latitudes and longitudes. 
        Those columns were dropped after their data were used to calculate the distance covered by bike riders.

Descriptive analysis using the Interquartile range method was also performed to exclude the datasets from ouliers.
Detailed information about the cleaning process are documented in the part 1 notebook of the project.

##### Storing Data

After cleaning the original dataset from both quality and tidyness issues, 
the cleaned dataset now contains 2.3 million records.

The cleaned dataset was read into a csv file named "bike.csv".
A 400,000 sample of the this dataset were collected and stored in bike_sample variable.
The bike_sample was created to reduce overplotting of data points on scatterplot.


## Summary of Findings

On exploring the time spent on each ride, I found that riders who spent 6 to 8 minutes 
on their rides are more than riders who spent lesser and more in the dataset. Compared to 
the entire population, only a few riders spent over 20 minutes on their rides.

After I took a log transformation of the frequency axis of the distribution 
of distance travelled, The information of the resulting distribution was similar to
the one without log transformation. It shows a negative correlation with the number of riders. 
The higher the distance bike riders covered the lesser the number of the riders covering the distance.

Distance increased drastically up to around 2.5 kilometer and then began to fall there after. 
It means that most of the riders didn't ride beyond 2.5 kilometer.

I also plotted the distance covered and time spent on the rides on scatter plot to 
find the relationship between them, the result was a very weak relationship. 
So, I took the cube root transformation of the duration against the distance covered 
on a scatter plot to see if I could get more details than the chart without the transformation. 
The result gave a better insight. The correlation between duration and distance was more obvious. 
The result was a more obvious positive correlation though not a very strong one.

On exploring the relationship between the categorical variables and dependent variables, 
I  found that among the two rider groups, the casual riders spent the most minutes on 
average on their trips than the suscribed members.

Among the three kinds of bikes driven by bike riders, docked bikes were 
driven longer in terms of time spent on trips than any other bike. Classic bikes were driven 
the least amount of time than any other bikes. Electric bikes covered the most distance while 
classic bikes covered the least distance.

On exploring the precise periods, days and months of the year the rides were taken, 
I found that both  casual and suscribed member riders ride mostly on saturdays.
Suscribed members least ride on sunday while  casual riders had the least rides 
on Monday, Tuesday and Wednesday.
I also found that the casual riders ride mostly in the afternoon and they least ride at late night. 
Lastly, the suscribed member had the highest number of rides in the month of october. 
Like the casual riders, they also had the least ride in february.


## Key Insights for Presentation

For the presentaion, I focused more on the distance travelled by bike riders,
time spent during those rides and how they relate to both groups of bike riders 
and the kind of bikes they ride. I used a boxplot to show the outcome.

I left out findings about the stations. I also include 
findings from the catgorical variables. Findings such as  how the riders ride in relative to 
each month of the year, days of the week and variouss periods of the day. 
I showed these results on a well labelled bar chart.

##### Limitaion
- I must mention that the exploration in this project does not imply causation. 
- Advanced exploration process such as prediction with machine learning algorithm  is required to make predictions.
- Also, I didn't consider the speed of bikes in this exploration to determine how fast the kinds of bikes are.
- I was unable to lay my hand on the weather dataset to make deeper findings on some of the variables.

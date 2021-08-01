# Bikesharing

## Overview of the analysis
A trip analysis was performed to solidify a bike sharing business proposal. The proposal will be presented to a potential angel investor interested in providing seed funding to explore a bike share project in Des Moines.   
<br />
The three technical deliverables required to complete the bikesharing analysis include <br />

1. Change Trip Duration to a Datetime Format.
2. Create Visualizations for the Trip Analysis.
3. Create a Story and Report for the Final Presentation.

## Resources
- Data Source: This analysis was performed using the  [201908-citibike-tripdata.cvs](https://s3.amazonaws.com/tripdata/index.html) dataset.
-  Code: [NYC_Citibike_Challenge.ipynb](https://github.com/aobasuyi/Bikesharing/blob/main/NYC_Citibike_Challenge.ipynb) 
- Data Tools: Jupyter Notebook, CSV, Tableau and IO (Web Server)
- Software: Jupyter Notebook and Visual Studio Code 1.50.0

## Results:
### Deliverable 1
#### Change Trip Duration to a Datetime Format: <br />
- Using Python and Pandas functions, convert the "tripduration" column from an integer to a datetime datatype. 
- Export the DataFrame as a CSV file to use for the trip analysis.
##### Code:
```
# Files to load
CitiBike_data_to_load = "201908-citibike-tripdata.csv"

# 1. Create a DataFrame for the 201908-citibike-tripdata data. 
CitiBike_df = pd.read_csv(CitiBike_data_to_load)
CitiBike_df.head()

# 2. Check the datatypes of your columns. 
CitiBike_df.dtypes

# 3. Convert the 'tripduration' column to datetime datatype.
CitiBike_df['tripduration_orig'] =CitiBike_df['tripduration']
CitiBike_df["tripduration"] = pd.to_datetime(CitiBike_df["tripduration"], unit='s')  

# 4. Check the datatypes of your columns. 
CitiBike_df.info()

# 5a. Create the output File (CSV)
output_data_file = "NewYork_CitiBike.csv"

# 5b. Export the Dataframe as a new CSV file without the index.
CitiBike_df.to_csv(output_data_file, index=False)

```

### Deliverable 2
#### Visualizations for the Trip Analysis: <br />

a).  How long are bikes checked out for all riders and genders?

| Checkout Times by Users  | Checkout Times by Gender |
| ------------- | ------------- |
| ![Top 10 starting](Resources/Visualization/Checkout_times_users.png)  | ![Top 10 ending](Resources/Visualization/Checkout_times_gender.png) |


- Most bike trips lasted less than one hour and the highest bike checkout time was about 6 minutes. 
- Males were 3 times more likely than females to use the bike rideshare.

<br /> 

b).  How many trips are taken by the hour for each day of the week, for all riders and genders?

| Trips by Weekday per Hour  | Trips by Gender (Weekday per Hour) |
| ------------- | ------------- |
| ![Top 10 starting](Resources/Visualization/Trips_weekday_hr.png)  | ![Top 10 ending](Resources/Visualization/Trips_weekday_gender.png)  |

- 8am, 5pm and 6pm are the peak rideshare hours on weekdays except for Wednesdays. 
- Saturdays peak hours start at 10am and lasts through 7pm.
- Males are more likely than females to use bike rideshare on weekdays.

<br />
c.) What days of the week will a user more likely check out a bike?

<br /> ![Image](Resources/Visualization/Trips_usertype_gender.png) <br />

- Male subscribers are more likely to use the ride bikeshare on all weekdays.
- Unknown customers are most likely to use the ride bikeshare on Saturdays.

### Deliverable 3
#### Tableau Story for the Final Presentation: <br />

- Create a story in Tableau and describes the key outcomes of the NYC Citibike analysis.
- Click this link to access the NYC Citibike analysis [NYC Citibike analysis dashboard](https://public.tableau.com/app/profile/pat1796/viz/DesMoinesCitiBikeProposal_16274868652750/CitiBikeProposal?publish=yes) 

##### Overview: 
<br /> ![Image](Resources/Dashboard_story/DesMoines_overview.png) <br />

- The image above shows that a typical bikeshare user is a male subscriber. As well, the average trip duration for bike ridesharing has been increasing steadily since the 1990s. 

##### Checkout Times:

<br /> ![Image](Resources/Dashboard_story/DesMoines_trip-duration_riders.png) <br />

- Male users are more likely to use the bike rideshare and most trips last less than 60 minutes

##### Weekday by hour:

<br /> ![Image](Resources/Dashboard_story/DesMoines_trips_weekday_hour.png) <br />

- Bike rideshare peak hours are 8 am, 5pm and 6 pm on weekdays except for Wednesdays. Males are most likely to use the bike rideshare compared to females.

 ##### Usertype and gender:
<br /> ![Image](Resources/Dashboard_story/DesMoines_trips_usertype.png) <br />

- Male subcribers are most likely to use bike rideshare on all weekdays compared to female subscribers. Unknown customers though are most likely to use the rideshare on Saturdays.

##### Top 10 stations:

| Top 10 starting stations  | Top 10 ending stations |
| ------------- | ------------- |
| ![Top 10 starting](Resources/Dashboard_story/DesMoines_top_starting_stations.png)  | ![Top 10 ending](Resources/Dashboard_story/DesMoines_top_ending_stations.png) |


- Pershing Square North is both the top starting and ending station for bike rideshares. 

##### Average Bike Utilization:

<br /> ![Image](Resources/Dashboard_story/DesMoines_bike_utilization.png) <br />

- Customers on average have the highest utilization of bikes. The top 3 bikeIDs used by customers are: 31443, 38540 and 19481.

## Summary:
- The average trip duration for bike ridesharing has increased steadily since 1990s.
- Male subscribers are most likely to use the bike rideshare for each hour and on weekdays.


##### Two additional visualizations suggested for future analysis:
 - Add a visualization that will predict the average trip utilization for the next five years
 - Determine top starting and stoping station by 
   -  usertype and gender to find ways to increase bike sharing use by both groups.
 



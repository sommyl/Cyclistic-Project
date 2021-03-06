# Sophie_Portfolio
Data Analytics Portfolio

# [Project 1: Cyclistic: Project Overview](https://github.com/sommyl/Sophie-Portfolio/blob/main/Cyclistic%20Project.md)
* Cyclistic is a bike share company based in Chicago.
* The business task is to provide insights for marketing strategies aimed at converting casual riders into annual members.

## Code Used
**SQL Github:** https://github.com/sommyl/Sophie-Portfolio/blob/main/Cyclistic.sql

**Tableau:** https://public.tableau.com/app/profile/sophie.liu3966/viz/Cyclistic_16450573041030/Story1

## Data Cleaning

The dataset contains 12 months rides information from Dec 2021 to Jan 2022 with 13 columns including

* Ride ID
* Bike type
* Start date and time
* End date and time 
* Start station name
* Start station ID
* End station name
* End station ID
* Start latitude
* Start longtitude
* End latitude
* End longtitude
* Member casual status

Following changes were made in the cleaning process

*	Created a new table and used union all function to merge 12 CSV files of monthly ride information with in total c. 5 million rows 
*	Created a new column for ride length as duration from start time to end time by using DATEDIFF fuction
*	Created a new column for day of the week from start date by utilising DATENAME function to convert YYYYMMDD HH:MM:SS date format into day of the week  
*	Shortened ride ID to save memory as this information is not critical
*	Removed columns "End date and time" and "Station ID" as this information is redundant 
*	Removed 2,207,583 rows for ride length less than 10 minutes as this is considered too short for trip length
*	Removed 4,754 rows with nil latittude and longtitude due to incomplete information for geographic mapping

## EDA & Visualisation 
Analysis is focused on observing difference in ride patterns between casual and member riders in order to derive insights for conversion strategy. All information given in the dataset has been utilised to construct analysis as follows
* Number of rides and ride length (derived from rider ID and time information) have been compared between casuals and members by frequency of month, day of the week and time of the day in order to identify the optimum period for advertising with widest reach 
* Start station and end station (pin dropped on the map based on latitude and longtitude) have been mapped out to find out concentration of ride locations between casuals and members and the optimum location for advertising

![alt text](https://github.com/sommyl/Sophie-Portfolio/blob/main/month.png "Number of Trips and Trip Length by Month")
![alt text](https://github.com/sommyl/Sophie-Portfolio/blob/main/weekday.png "Number of Trips and Trip Length by Day of the Week")
![alt text](https://github.com/sommyl/Sophie-Portfolio/blob/main/hour.png "Number of Trips and Trip Length by Hour")
![alt text](https://github.com/sommyl/Sophie-Portfolio/blob/main/map.png "Map of Start and End Location")

## Recommendation
In order to achieve maximum reach of casual riders, it is recommended that 
* Advertisement is to be placed **during summer season** **on the weekend** **from 12pm to 5pm** as data indicated that this is when casual riders are most active measured by average number of trips taken.
* The ideal location for advertising is **in Harbour and Millennium Park area** which captures higher density of start and end point for casual riders.
* With regards to the observation that casuals takes longer rides in kms than members, the company could notify and acknowledge the milestones in km's achieved at the end of each ride to incentivise future rides which may subsequently result in member conversion. (idea)

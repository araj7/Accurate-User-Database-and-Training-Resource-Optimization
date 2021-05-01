# Accurate-User-Database-and-Training-Resource-Optimization

## Introduction
One of the Accenture's Federal clients has a global supply chain and the system that they maintain for client tracks the procurement, distribution, maintenance, and retirement of their assets. The system contains more than 10 years of data. Every user in their system is assigned different roles based on the functions that they need to perform. The goal of this project is to Create a dashboard that can be broken down by location that gives a list of the users that need training and the training area sorted by urgency.

### Preprocessing and Modeling

#### Training Disposals
* Removed duplicates
* Changed the datatypes
* Imputed the missing data
* Created additional columns based on the calculations that we did from the preexisting ones
* Removed the unnessacary columns
* Performed some mathematical calculations to find the weights for disposal roles
* Standardized the error cost column using the StandardScaler
* Normalized every other feature using the MinMaxScaler()
* Merged the orginal total cost to the result for reference
* Outer join two tables "top 10 highest scoring users" and orginal total cost and result tables by using common field "user"
* Removed the duplicate rows
* Generated new dashboard
* Renamed the new columns
* Removed the dupicate rows

#### Training Locations
* Checked and imputed the missing values
* Removed duplicate rows
* Corrected the data types of the attrubutes
* Removed unwanted punctuations
* Imputed the NaN values with 0
* Create new table to continue modeling
* Assigning weights to the location columns
* Standardized the role location column by using StandardScaler()
* Normalized every feature by using MinMaxScaler()
* Assigned weights to every attribute
* Merged the orginal total cost to the result for reference
* Displayed reeults in a table in descending order
* Displayed the top 10 users with highest socres in a table
* Merged the two tables with outer join using a common field user
* Removed all the missing values
* Removed the duplicate rows
* Genereted new dashboard
* Adjusted column names
* Displayed the results by score from large to small
* Displayed the records that rating >= 0
* Display the results by score from large to small

#### Training Receieving
* Checked for missing values and imputed with 0
* Removed duplicate rows
* Removed unwanted punctuations
* Fixed the datatypes
* Assigned weights to the role receiving
* Standerdized the error cost feature using StandardScaler()
* Normalized rest of the features using MinMaxScaler()
* Displayed the results by score from large to small
* Display top 10 users that have the higher scores
* Outer join two tables by using common field "user"
* Generated new dashboard
* Renamed the columns
* Show results by score from large to small
* Select user records that have rating >= 0
* Outer join the three table, using a common field "user"
* Checked if there is missing value (missing value here has a meaning, which means the user doesnt have specific role)
* Calculating the total rating
* Displayed the top 10 highest scoring users
* Generated new table
* Displayed if the user has a specific role. If he has a role, the value = 1
* Displayed the top 10 highest scoring users
* Displayed the top 10 location in role disposals
* Displayed the top 10 location in role location
* Displayed the top 10 location in role receiving
* Calculated the total rating
* Sorted the location id in descending order
* Display the results by score from large to small
* Export table to s3 to create dashboard

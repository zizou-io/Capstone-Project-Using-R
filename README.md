# Capstone-Project-Using-R

---

## Background
In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown to a fleet of 5,824 bicycles that are geotracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station in the system anytime. Until now, Cyclistic’s marketing strategy relied on building general awareness and appealing to broad consumer segments. One approach that helped make these things possible was the flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships. Customers who purchase single-ride or full-day passes are referred to as casual riders. Customers who purchase annual memberships are Cyclistic members.

---

## 1. Ask

***Business Question:***

How do annual members and casual riders use Cyclistic bikes differently?

***Key Stakeholders:***

* Lily Moreno
* Cyclistic marketing analytics team
* Cyclistic executive team

***Business Task:***

Use the data to explore and gain insights on how annual members and casual riders use bikes differently. From trends and insights, assist the team to implement marketing strategies aimed at converting casual riders into annual members.

---

## 2. Prepare

The data include information about Cyclistic's historical trip and customers' patterns in bike usage. It is obtained between April 2022 and March 2023 (12 months).

Link: [Data Source](https://divvy-tripdata.s3.amazonaws.com/index.html)

---

## 3. Process

Due to the large amount of data and flexibility of R language, I will process the data with R Studio to work with the data more efficiently. This will be applied to data cleaning, analysis, and visualization.

### Data Preparation

* Libraries: tidyverse, lubridate, ggplot2
* Data are stored in CSV format and imported separately by months
* Checked data columns for name consistencies
* 12 months of data are merged into a single dataframe

### Date Cleaning

* Created additional columns (date, month, day, year, and day of week) for data analysis
* Removed start_lat, start_lng, end_lat, and end_lng columns from the data
* Got rid of missing values using `na.omit()`
* Created a ride length column in minutes with `difftime()`
* Converted the ride length column into a numeric
* Removed and filtered the data so that it does not include values with negative or zero ride lengths
* Ordered the day of the week column

---

## 4. Analyze

The analysis phase will explore the question "How do annual members and casual riders use Cyclistic bikes differently?" by performing descriptive statistical analysis and aggregating the data with group by to extract trends from bike users.

### Descriptive analysis

* Calculated the mean, median, min, and max on ride length column
* For each member types, I explored the average, min, and max ride length

### Data aggregation

* Explored the members type by looking at the count between annual vs. casual members
* Count number of each bikes type
* Group by members and bikes type to find to total count
* Count number of rides of weekday based on members type
* Calculated the average ride length by bike and member type
* Calculated the average of ride length for each member types based on week day

---

## 5. Share
After analyzing the data, I visualize the data with pie chart and bar graphs to discern the differences in bike patterns visually between member and casual riders. Data visualization is a powerful tool to draw insights quickly

#### Visualization #1: Percentage Distribution of Annual and Casual Riders
<img width="600" alt="Annual vs  Casual Pie Chart" src="https://github.com/hoang-nguyen1/Google-Data-Analytics-Capstone-Project/assets/81605575/cb060111-5ca2-40ba-826c-6023cff24f3e">

* *Overall, there are more member than casual riders (60% vs. 40%).*


#### Visualization #2: Total Number of Rides by Bike and Member Types
<img width="600" alt="Screenshot 2023-05-15 at 12 30 56 PM" src="https://github.com/hoang-nguyen1/Google-Data-Analytics-Capstone-Project/assets/81605575/872c6113-7c33-4965-b920-3aaedb3264bb">

* *Between these three bikes (classic bike, docked bike, and electric bike), classic bike is the most popular type of bike among member and casual riders. Furthermore, members have higher number of rides for classic and electric bikes than casual riders (due to larger proportion of members). Unlike casual riders, they do not use docked bikes.*


#### Visualization #3: Total Number of Rides by Member Types and Day of Week

<img width="600" alt="Screenshot 2023-05-15 at 12 46 26 PM" src="https://github.com/hoang-nguyen1/Google-Data-Analytics-Capstone-Project/assets/81605575/c8411f56-02fe-47d4-b48d-2a9b4bccd3f9">

* *During weekdays, there are high amount of bike usage among members compared to casual riders. However, casual riders increase their bike usage in the weekend.*


#### Visualization #4: Total Number of Rides by Member Types and Month

<img width="600" alt="Screenshot 2023-05-15 at 12 55 03 PM" src="https://github.com/hoang-nguyen1/Google-Data-Analytics-Capstone-Project/assets/81605575/1c928694-c2dc-4d92-8244-ae6091c66ed0">

* *For both member and casual riders, bike usage is lowest in the beginning and at the end of the year (January-April and November-December). These members prefer to use bikes throughout  the middle of the year, which indicate they have higher preferences in bike usage during the summer and fall.*


#### Visualization #5: Average Ride Duration Spent by Member Types

<img width="600" alt="Screenshot 2023-05-15 at 1 03 15 PM" src="https://github.com/hoang-nguyen1/Google-Data-Analytics-Capstone-Project/assets/81605575/fa7532c4-7b84-4dac-9d99-1b58ebcf6fe9">

* *On average, casual riders spend roughly two times more than members in riding bikes (indicated in minutes).*


#### Visualization #6: Average Ride Duration Spent by Member and Bike Types

<img width="600" alt="Screenshot 2023-05-15 at 1 08 14 PM" src="https://github.com/hoang-nguyen1/Google-Data-Analytics-Capstone-Project/assets/81605575/ad26ef5a-496a-403d-8ef9-1f862f7e20a7">

* *Members spend significantly less minutes in all the bikes compared to casual riders and they do not use docked bikes at all. In addition, casual riders spend the most time on docked bikes in relative to other bikes.*

---

## 6. Act

### Conclusion
After analyzing and visualizing the data, some major findings that I found were a larger percentage of members compared to casual riders, higher preferences for classic bike for riders, popularity in bike usage during summer and fall, and higher average ride duration for casual riders. Additionally, docked bike is the least popular bike due its long riding time as indicated by the average spent time in casual riders. 

### Recommendations

* Due to high popularity in bike usage throughout the summer and early fall, it would be a good idea to launch a **incentive campaign** to maintain or increase bike usage
* Casual riders spend more time in riding bike, therefore providing some kind of **discounts or promotions** for electric bike would help them save some time
* Launch **marketing campaign** that target the benefits of converting into annual membership for casual riders through advertisements, emails, and brochures

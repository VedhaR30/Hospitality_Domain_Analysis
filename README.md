#                                                                 🏨 AltiQ Hospitality Analysis
![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
## Introduction
Welcome to the Hospitality Power BI Dashboard repository! This project aims to provide a comprehensive and insightful visualization solution tailored for the hospitality industry. Whether you are a hotel manager, event planner, or hospitality data enthusiast, this Power BI dashboard offers key metrics and analytics to empower better decision-making and enhance operational efficiency.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
## Data Transformation
Abhishek Anand is a Revenue Manager of the Hotel who is our stackholder has provided us the Data. We have firstly loaded this Data in Power BI. Than with the use of power query in Power BI we have Performed Data Preprocessing and Data Cleaning to Transform the data so that it can be used for computing insights from it.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
## Data Modelling

Data Modeling is performed on all the Datasets using Power BI. Datasets are being connected to each other based on the defined primary keys of the Datasets.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## Data Analysis Expression (DAX)
Created Measures using Data Analysis Expression (DAX) in Power BI. Measures and calculated coloumns created are as follows :

- Revenue: `SUM(fact_bookings[revenue_realized])`
- Total_Bookings: `COUNT(fact_bookings[booking_id])`
- Total_Capacity: `SUM(fact_aggregated_bookings[capacity])`
- Total_Successful_Bookings: `SUM(fact_aggregated_bookings[successful_bookings])`
- Occupancy %: `DIVIDE([Total_Bookings], [Total_Capacity], 0)`
- Average_Rating: `AVERAGE(fact_bookings[ratings_given])`
- No_of_days: `DATEDIFF(MIN(dim_date[date]), MAX(dim_date[date]), DAY) + 1`
- Total_Cancelled_Bookings: `CALCULATE([Total_Bookings], fact_bookings[booking_status]="Cancelled")`
- Cancellation %: `DIVIDE([Total_Cancelled_Bookings], [Total_Bookings])`
- Total_Checked_Out: `CALCULATE([Total_Bookings], fact_bookings[booking_status]="Checked Out")`
- Total_No_Show_Bookings: `CALCULATE([Total_Bookings], fact_bookings[booking_status]="No Show")`
- No_Show_Rate %: `DIVIDE([Total_No_Show_Bookings], [Total_Bookings])`
- Booking % _by_Platform: `DIVIDE([Total_Bookings], CALCULATE([Total_Bookings], ALL(fact_bookings[booking_platform]))) * 100`
- Booking % _by_Room Class: `DIVIDE([Total_Bookings], CALCULATE([Total_Bookings], ALL(dim_rooms[room_class]))) * 100`
- ADR (Average Daily Rate): `DIVIDE([Revenue], [Total_Bookings], 0)`
- Realisation %: `1 - ([Cancellation %] + [No_Show_Rate %])`
- RevPAR (Revenue per Available Room): `DIVIDE([Revenue], [Total_Capacity])`
- DBRN (Daily Bookings Rate per No of Days): `DIVIDE([Total_Bookings], [No_of_days])`
- DSRN (Daily Stay Rate per No of Days): `DIVIDE([Total_Capacity], [No_of_days])`
- DURN (Daily Checked Out Rate per No of Days): `DIVIDE([Total_Checked_Out], [No_of_days])`
- Revenue_WoW_Change %: `A week-over-week change for Revenue`
- Occupancy_WoW_Change %: `A week-over-week change for Occupancy`
- ADR_WoW_Change %: `A week-over-week change for ADR`
- RevPAR_WoW_Change %: `A week-over-week change for RevPAR`
- Realisation_WoW_Change %: `A week-over-week change for Realisation`
- DSRN_WoW_Change %: `A week-over-week change for DSRN`

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
## Dashboard

Dashboard is created after creating the DAX measures. For creating this Dashboard Power BI Destop is used.

!## 📊 Dashboard Preview

![AltiQ_Hospitality_Dashboard](https://github.com/VedhaR30/Hospitality_Domain_Analysis/blob/e9bd14c36d63980c85f123e39d23576be0af97ae/AltiQ_Hospitality_Dashboard.png)

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## Reference

* Channel Name : codebasics
* Link to the Project : [https://www.youtube.com/watch?v=4QkYy1wANXA](https://www.youtube.com/watch?v=tT4V7zguCnc&t=33s)

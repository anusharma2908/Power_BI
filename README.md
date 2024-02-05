# Car Sales - Dashboard

# Dashboard Overview
![image](https://github.com/anusharma2908/Power_BI/assets/157443748/20e1b9ad-b0e3-4c9a-a4ce-368bc3036722)

## Background: Our company is a car dealership that sells various car models. To effectively track and analyse our sales performance, we need a comprehensive Car Sales Dashboard in Power BI. 

## Objective: The objective of this project is to design and develop a dynamic and interactive Car Sales Dashboard using Power BI. The dashboard will visualize critical KPIs related to our car sales, helping us understand our sales performance over time and make data-driven decisions.

## Problem Statement 1: KPI’s Requirement

The dashboard should provide real-time insights into key performance indicators (KPIs) related to our sales data. This will enable us to make informed decisions, monitor our progress, and identify trends and opportunities for growth.

1.	Sales Overview:
•	Year-to-Date (YTD) Total Sales
•	Month-to-Date (MTD) Total Sales
•	Year-over-Year (YOY) Growth in Total Sales
•	Difference between YTD Sales and Previous Year-to-Date (PTYD) Sales

2.	Average Price Analysis:
•	YTD Average Price
•	MTD Average Price
•	YOY Growth in Average Price
•	Difference between YTD Average Price and PTYD Average Price

3.	Cars Sold Metrics:
•	YTD Cars Sold
•	MTD Cars Sold
•	YOY Growth in Cars Sold
•	Difference between YTD Cars Sold and PTYD Cars Sold


## Problem Statement 2: Charts Requirement

1.	YTD Sales Weekly Trend: Display a line chart illustrating the weekly trend of YTD sales. The X-axis should represent weeks, and the Y-axis should show the total sales amount.
2.	YTD Total Sales by Body Style: Visualize the distribution of YTD total sales across different car body styles using a Pie chart.
3.	YTD Total Sales by Color: Present the contribution of various car colors to the YTD total sales through a pie chart.
4.	YTD Cars Sold by Dealer Region: Showcase the YTD sales data based on different dealer regions using a map chart to visualize the sales distribution geographically.
5.	Company-Wise Sales Trend in Grid Form: Provide a tabular grid that displays the sales trend for each company. The grid should showcase the company name along with their YTD sales figures.

### Summary Overview

![Sales Dashboard](https://github.com/anusharma2908/Power_BI/assets/157443748/dce83245-b903-4650-8ed9-4e1a08f08798)

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a excel file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present.
- Step 5 : A new Calendar Table was created to show Dates between min and max values of [Date] column of Car_Sales data.
- Step 6 : In the report view, under the view tab, theme was selected.
- Step 7 : Visual filters (Slicers) were added for four fields named "Body Style", "Dealer Name", "Transmission" & "Engine".
- Step 8 : In the report view, under the insert tab, a text box was inserted & dashboard title was added.
- Step 9 : Various new measures were created to calculate metrics for "Sales Overview" , "Average Price Analysis" and "No of Cars Sold overview".

Following DAX expressions were written: 
        
        YTD Total Sales = TOTALYTD(sum(car_data[Price ($)]),'Calendar Table'[Date])
	PYTD Total Sales = CALCULATE(sum(car_data[Price ($)]),SAMEPERIODLASTYEAR('Calendar Table'[Date]))
	Sales Diff = [YTD Total Sales]-[PYTD Total Sales]
	MTD Total Sales = TOTALMTD(sum(car_data[Price ($)]),'Calendar Table'[Date])
	YTD Avg Price = TOTALYTD([Avg Price],'Calendar Table'[Date])
	PYTD Avg Price = CALCULATE([Avg Price],SAMEPERIODLASTYEAR('Calendar Table'[Date]))
	Avg Price Diff = [YTD Avg Price]-[PYTD Avg Price]
	MTD Avg Price = TOTALMTD([Avg Price],'Calendar Table'[Date])
	YTD Cars sold = TOTALYTD(count(car_data[Car_id]),'Calendar Table'[Date])
	PYTD Cars Sold = CALCULATE(count(car_data[Car_id]),SAMEPERIODLASTYEAR('Calendar Table'[Date]))
	Cars sold Diff = [YTD Cars sold]-[PYTD Cars Sold]
	MTD Cars sold = TOTALMTD(count(car_data[Car_id]),'Calendar Table'[Date])
        
The card visuals were used to represent the above metrics.

       
- Step 10 : Conditional formatting was applied on vPYTD and %vPYTD growth metrics.
 
 
- Step 11 : An area chart was created to show YTD Sales Weekly Trend along with the Max Point value.

- Step 12 : A donut chart was created to show YTD Total Sales by Body Style.

- Step 13 : A donut chart was created to show YTD Total Sales by color.

- Step 14 : A map chart was created to show YTD Cars Sold by Dealer Region.

- Step 15 : A table was created to display the sales trend for each company. The grid showcases the company name along with their YTD sales figures.



# Insights

A single page summary was created on Power BI Desktop:

Following inferences can be drawn from the dashboard;

### 
1.	Sales Overview:
•	Year-to-Date (YTD) Total Sales = $371.2M
•	Month-to-Date (MTD) Total Sales = $54.3M
•	Year-over-Year (YOY) Growth in Total Sales = 23.6%
•	Difference between YTD Sales and Previous Year-to-Date (PTYD) Sales = $70.8M

2.	Average Price Analysis:
•	YTD Average Price = $28.0k
•	MTD Average Price = $28.3k
•	YOY Growth in Average Price = -0.8%
•	Difference between YTD Average Price and PTYD Average Price = -$0.2k

3.	Cars Sold Metrics:
•	YTD Cars Sold = 13k
•	MTD Cars Sold = 2k
•	YOY Growth in Cars Sold = 24.6%
•	Difference between YTD Cars Sold and PTYD Cars Sold = 2.6k



 ### Some other insights
 
 ### Body Style
 
 1.1) 27 % customers prefer buying SUV.
 
 1.2) 22 % customers prefer hatchback.
 
 1.3) 20 % customers prefer sedan.

 
 
 ### Color
 
 2.1)  47 % customers choose White color.
 
 2.2)  34 % customers choose Black color.
 
 2.3)  19 % customers choose Red color.

         
### Dealer region

3.1) 2296 cars were sold in Austin region.

3.2) 2113 cars were sold in Janesville.

3.3) 1912 cars were sold in Scottsdale.
       



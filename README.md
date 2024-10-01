# Walmart-Dashboard

## Description

Walmart is an American multinational retail corporation that operates a chain of hypermarkets (also called supercenters), discount department stores, and grocery stores in the United States and 23 other countries. It is headquartered in Bentonville, Arkansas.

Walmart is the world's largest company by revenue, according to the Fortune Global 500 list in October 2022. Walmart is also the largest private employer in the world with 2.1 million employees. It is a publicly traded family-owned business.

Walmart's investments outside the U.S. have seen mixed results. Its operations and subsidiaries in Canada, the United Kingdom (ASDA), Central America, South America, and China are successful, but its ventures failed in Germany, Japan, South Korea, Brazil and Argentina


## Problem Statement

This dashboard help to understand customers and their choices better. It helps to  know, their sales and profit/loss. Through different analysis, they get to know their improvement area, & thus they can improve their sales by promotions and rewards in identified areas. It also let them know their average sales state wise and profits per year. Thus by using this dashboard they can identify the problem, and they can further work on factors responsible for it .

Since, number of customers in other sates are very less compared to California, they must work on improving their services in identified states. 

Also shipping delay's can be addressed, As ship date is minimum 5 days from order date, they must try to reduce it.

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Data set used :-                                                        

https://raw.githubusercontent.com/LokeshKumarChauhan/DE_with_powerBI/main/Walmart.csv 

- Step 3 : Script to download the dataset from API to Power BI :-
      
import pandas as pd

url="https://raw.githubusercontent.com/LokeshKumarChauhan/DE_with_powerBI/main/Walmart.csv"
df=pd.read_csv(url)
print(df)

- Step 4 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 5 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 6 : It was observed that in none of the columns errors & empty values were present. 
- Step 7 : A new column called "Year" is added to the existing table from "order date" column to extract year and compare the sales by year.
  
   for creating new column following DAX expression was written:          
           year = year('df (2)'[Order Date])

- Step 8 : In the report view, under the view tab, theme was selected.
- Step 9 : Since the data contains several subcategory items, a new visual was added using donut chart in the visualizations pane in report view. While creating this visual, field named 'subcategory' is added to the Legends, thus sum of sales is segregated according to the category. 
- Step 10 : Gauge is added to represent the sum of sales of a particular sub category.  
- Step 11 : Four card visuals were added to the canvas, representing Total customers, Total sales, Total profit and number of categories.
- Step 12 : A Pie chart is added to show the sum  of the profit of individual subcategory, which can help to improve the sales.
- Step 13 : A bar chart was also added to the report design area representing the sum of sales by state. 
- Step 14 :A Funnel is added to showcase  the year wise profit to compare and improve the sales 

In our dataset, discount column has some values assigned 0, representing those parameters are not applicable for some customers. All these values have been ignored while calculating.

- Step 15 : The report was then published to Power BI Service.
 
 
## Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

#### [1] Total Number of Customers = 686

#### [2] Total sales = 2348

#### [3] Total Profit = 108.42k
  
#### [4] Most selling products in each category

 
### Furniture

 1.1) 14.03 % customers have purchased Chairs.

 1.2) 11.68 % customers have purchased Tables.

 1.3) 9.72 % customers purchased Storage


### Technology
 
 2.1)  13.6 % customers purchased Phones.
 
 2.2)  5.85 % customers purchased Machines.
 
 2.3)  4.17 % customers purchased Appliances.
 
      thus, phones is the second most purchased item


### Office Supplies
 
 3.1) 8.42 % customers purchased Accessories.
 
 3.2) 7.71 % customers purchased Binders.

 3.3) 6.86 % customers purchased Copiers.

       
       thus, more customers have purchased items from Furniture Category.




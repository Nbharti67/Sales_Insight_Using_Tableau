# Sales_Insight_Using_Tableau

Introduction:
There is a virtual company whose sales data has been provided to us and our aim is to find sales insight so that we can check whether sales is declining or not and
if sales is declining what can be done to increase the profit. We'll be looking on these aspects.

## Purpose
To unlock sales insights that are not visible before for sales team for decision support & automate them to reduce manual time spent in data gathering
## Stakeholders
- Sales Director
- Marketing Team
- Customer Service Team
- Data & Analytics Team
- IT

## End Result
An automated dashboard providing quick and latest sales and profit insights in order to support data-driven decision making

## Success Criteria
- Dashboards uncovering sales order insights with the latest data available
- Sales team able to take better decisions and prove 10% cost savings of total spend
- Sales analyst stop data gathering manually in order to save 20% of their business time and reinvent it value-added activity

## Process that has been followed to create the dasboard.
### Data Preparation and cleaning
- Data is in .sql format. So first of all, we will import data in MySQL workbench and then will make a connection between SQL and tableau to import data 
from SQL to tableau
- Then, we will create a data model (star schema) in Tableau
- Now the relationship between the data tables of the dataset is created, we will clean the data.

- In Transaction table:
1. Sales amount has -1 and 0 as selling amount so we'll remove all -1 and 0 by applying filter that contains sales amount atleast 1, should not be less than 1
2. Now, we will check sales quantity (sales quantity shouldn’t have any 0 or -1). if there is any 0 or -1 as sales quantity, we'll filter it 
(To filter it follow the step shown here in tableau: go to data->edit data source filters)
3. Again, while checking, I found that sales amount is in USD for some sales, so I need to change into INR so for this do the step below

Step to change sales amount in USD to INR using Tableau Desktop is below:

Click on dropdown from column and select calculated field, -> Name the calculated field as Normalized amount and write formula below

IF [Currency] == 'USD' THEN [Sales Amount]*81.74 ELSE [Sales Amount] END

- In market table:

The company has market in India only so if we find any city not situated in India, we'll delete those rows.

## Data Analysis and visualization
Since the data is clean now, we create below visualization to find insights from them
- Revenue breakdown by cities
- Sales quantity breakdown by city
- Revenue breakdown by years and months
- Top 5 customers by revenue and sales quantity



From the Dashboard - Revenue Analysis, we can conclude that sales are declining. Next question arises that What is our opinion as an analyst to increase the profit 
or what is the decision we suggest to pickup our business.

Now as we know sales are declining, we created below charts to find how can we increase the profit
- Revenue breakdown by cities
- Profit breakdown by cities
- Profit trend by years and months
- Sales amount and profit foe each customers
- Total percent of customer by their types.

 profit_margin in the dashboard = profit*100/sales_amount 

## Conclusion from Tableau dashboards:
We can conclude from the Dashboard - Revenue Analysis is that sales are declining.

To increase the profit we concluded below from Dashboard-Profit Analysis
- We should increase revenue for bhubneshwar, Surat since even if revenue is low, these cities are giving high profit.

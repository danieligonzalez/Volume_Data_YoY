# Volume Data Year over Year

For this project the objective was to identify how volume had changed year over year from Q2 2020 to Q2 2021.

Here is the original request...

"The board is asking to see how volume looked in Q2. I got some data (attached), but didn’t have a chance to pull anything together and was hoping you could take a stab at it.

I think they just want to see Q2 2021 volume by region and wanted to know if everything was looking good. I think this file has what you need. I don’t remember all the region codes – I know NAM ends in 1, EMEA ends in 3 and APAC and LATAM are 2 and 4, but I don’t remember which is which. I do know LATAM has the lowest volume so just go ahead and assign that to which ever comes out lowest."

## Ask
To start off it was important to clarify the objective and set clear goals for the project.

The goal was to find volume by region and compare Year over Year to determine if Q2 2021 is looking good.

## Prepare
### V1 Excel File
The data tables were not to big for EXCEL.  There were 2 tables, one for Volume Data and another for GEO Data.  Region codes were not attached to clients, but the GEO codes helped determine Region according to the original request.

In the V1 Excel file there are a 6 tabs.  One is the original email request, 2 are the original data tables, 2 are the cleaned data tables, and 1 is a pivot table.

On the original Volume Data tab the Client ID (CLID) was not matched to each transaction.  I started by filling the blanks for CLID to the transactions.

For the GEO Data original tab the Client ID column had an extra C & - to the actual Client ID.  I removed the C- with a MID function and again with a RIGHT function and then made an extra column to see if the MID and RIGHT columns matched.  They all came back as TRUE.

## Process
### V1 Excel File
Client ID, Region Codes, Dates/Quarters

On the Volume Data tabe I matched the GEOID column to the CLID column (the CLID column on both tabs at this point were fomatted the same) using an XLookup function and then an INDEX match function to confirm.

This then allowed me to created a Pivot Table to get the SUM of the Volume to determine which Region Code beloned to which GEO Code.  I then made a column on each tab matching the code with a VLookup function.

Then I made a Date Table on the Volume Data Tab to match with each transaction so that I could Analyze by Quarter.  I added 2 columns to match Quarter with transactions with a Roundup function and Vlookup function.

## Analyze 
### V2 Excel File
Pivot Tables

I created a Pivot Table off the Volume Data Tab.  Started off by making columns based off Years & Quarters, then set the Rows to the Region Codes and added the SUM of Volume.

I copied that pivot table and expanded below to see all the transactions.

Below that I used COUNTIFS functions to see how many active clients there were by region.  Then I divided the number of Clients by the Volume to determine average Volume per Client.

Looking at the difference in overall volume from Q1 Year over Year and Q2 Year over Year, you could see a drop in growth.  

2 Customers left region in Q2, taking about 7k in volume away.
Q2 YoY growth slowed from Q1 growth of 4% down to 2.7% primarily driven by:
-.7% or 7k volume decline from loss of two customers in LATAM driving overall growth for region down from 9% in Q1 to flat in Q2 YoY.
same store sales slower than expected in Q2 vs Q1 YoY, comprising majority of remaining variance.

## Share
### V3 Excel File
Visualizations & Insights

I used a dounut chart to display the volume as of Q2 2021 separated by Region, and then another dounut chart to display number of Customers as of Q2 2021 by Region.

To the right there is a bar chart displaying the Volume Year over Year for both Q1 & Q2.

Below are some tables displaying Volume by Region, Number of Customers by Region, and Average Volume per Customer by Region.  To the right of each table is the Year over Year growth and decline.

For the Volume Table I used SUMIFS functions to get the Data from the cleaned Volume & GEO data tabs.
For the Customers Table I used ROUNDUP functions based on the Volume Table to determine the number of customers.
For the Average Volume/Customer Table I divided the Volume by the Customers Tables.

Key Notes:
Q2 YoY growth slowed from Q1 growth of 4% down to 2.7% primarily driven by:
- 7k volume, or 55% of the decline from loss of two customers in LATAM, driving overall growth for region down from 9% in Q1 to flat in Q2 YoY
- NAM client onboarding in Q2 2020 anniversaried in Q2 2021, slowing perceived growth and amplifying Q1 growth by ~5k units

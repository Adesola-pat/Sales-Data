# LITA PROJECT(SALES DATA)
---
## Data Analysis
---
## Outline
---
[Overview](#overview)

[Tools Used](#tools-used)

[Data Cleaning and Preparation](#data-cleaning-and-preparation)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Data Analysis](#data-analysis)

[Data Visualization](#data-analysis)

#### Overview
---
Here,i have an explicit detail of the steps used in the analysis of Sales Data for my LITA project.

### Tools Used
---
Tools used includes:
- Microsoft Excel [Download here](https://www.microsoft.com)
  1. for Data Cleaning
  2. For Data Analysis
  3. For Data Visualization
- Structured-Query-Language (SQL) for Data Query
- PowerBI for Data Visualization

### Data Cleaning and Preparation
---
Before any analysis can be done, data must first be Extracted, Transformed and then load (ETL)
- Extraction involves pulling data from a database
- Transforming a data set is making a data set suitable for analysis and this can be by removal of excesses, trimming and addition.
- Loading is to upload the transformed data set to where its going to be analysed i.e to the system used for analysis.
- I also validate the data set
  
### Exploratory Data Analysis
---
This inolves exploring amd manipulation of data to answer some questions as carried out in Excel. Such as;
 1. What Region has the lowest sales recorded?
 2. Which Product has the highest revenue?
 3. What is the average revenue generated per product?

### Data Analysis
---
This has to do with the several functions or line of codes (queries) used during the Analysis to query the data set;

```SQL
-----total revenue by subscription type------
select [SubscriptionType],
SUM([Revenue]) as totalRevenue
from [dbo].[LITA Capstone Project]
group by [SubscriptionType];

-------top 3 regions by subscription cancellation-----
select top 3 'Region'
count '[CustomerID]' as
cancellations
from [dbo].[LITA Capstone Project]
where cancelled =1
group by [Region]
order by cancellations desc;

------ total number of active and cancelled subscription-----
select
	sum(case when cancelled = 0
then 1 else 0 end) as
activesubscriptions,
	sum(case when cancelled =1
Then 1 else 0 end) as
cancelledsubscriptions
from [dbo].[LITA Capstone Project]
```

### Data Visualization
---
This is where we have a visual display of all results generated after the analysis.
This also includes reports from pivot table and PowerBi

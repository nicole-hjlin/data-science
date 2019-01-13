# Visualizing International Education 

---

## IMPORTANT NOTE
_report.ipynb_ contains interactive plots that cannot be shown in github browser yet. 
- Please **click the following link** for the final report that displays all plots properly: [https://nbviewer.jupyter.org/github/nicole-hjlin/exploratory-data-analysis/blob/master/world-bank-international-education/report.ipynb](https://nbviewer.jupyter.org/github/nicole-hjlin/exploratory-data-analysis/blob/master/world-bank-international-education/report.ipynb)
- Alternatively, pull the whole repo and run the jupyter notebook locally. 

- This report is work in progress and your feedback will be highly appreciated. You can contact me at GitHub or by email(nicole.hjlin@gmail.com)

---

## Introduction and Data Description

This report is created for the following **objective**:
> to explore a _diverse_ set of modern data acqusition, management, processing, visualising, and modelling tools, and apply the appropriate methods on a real world dataset.

With this goal in mind, I chose the [World Bank International Education dataset](https://console.cloud.google.com/marketplace/details/the-world-bank/education) as my main data, which is hosted as a public dataset on [Google BigQuery](https://cloud.google.com/bigquery/). Google BigQuery is a data warehousing service provided by Google Cloud. Datatsets are reshaped into SQL databases and accessed using SQL queries.

Besides for the international education dataset, I also downloaded world population data as a csv file from the World Bank data bank website, and web-scrapped the numbers of countries of different country groups. 

### Overview of the main dataset: 

> The dataset is originally complied by the World Bank from various sources, including public surveys and private foundations. The dataset combines key statistics on education attainment, expenditures, literacy, and so on. It contains country-specific data aross time (year). In specific, one row of the international education table looks like this: 

| country_code | country_name | indicator_name | indicator_code | year | value|
|---|---|---|---|---|---|
| AGO | Angalo | Barro-Lee: Average years of secondary schooling, age 15+, total | BAR.SEC.SCHL.15UP | 2010 | xxx|


> The dataset is about 600MB, containing over 3600 indicators and over 5 million datapoints (rows), which makes the traditional way of downloading and uploading the dataset undesirable. 

Besdies for the size of the dataset, many challenges arise when I try to analyze this dataset.

### Main challenges and my approaches:
    
- **Google BigQuery is not an entirely free service:**
    
    Only the first 1TB/month is free for each user. Therefore, the size of queries matter. 
    To avoid depleting my free quota, I check the size of each query before I run it to get data. 
    To avoid using the same query more than once, I use pickle to save the results for future processing and visulization.  
       
       
- **There are over 3600 indicators:**
    
    Many of them are overlapping or have very few datapoints. 
    To ensure the quality of my results, I first count the number of datapoints for each indicator, filter out those with less than 1000 datapoints, group the remaining indicators by topics, select interesting topics to visualize, and visualize selected indicators under different topics. 
    
    
- **Datapoints are not consistent for some indicators:**
    
    Countries might have data for different years, and vice versa. Some years might have fewer datapoints than the others. For example, for education expenditures, year 2010 might have 100 countries' data available, while 1990 only has 20. Additionally, some countries could also have different datapoints from the others. For example, for the same indicator, the UK might have 20 data points from 1990 to 2010, while Malawi only has one datapoint for 2010. 
    
    To maintain consistency of my results, I first count the number of datapoints for each year, select a period that has more datapoints, and subset the dataset based on the selected period. Given the period, I then count the number of datapoints for each country, select those have data for the whole period, and subset the dataset based on selected countries.
    
### Summary of tools:
- **Data acqusition and management**:

    - Google BigQuery API--to establish connection with the database
    - SQL queries--to access and retrieve data
    - Pickle--to save dataframe objects 
    - Pandas--to make dataframe objects and read csv file 
    - Request and BeautifulSoup--to webscrap information on websites


- **Data processing and reshaping**:

    - Pandas: dropna, merge, melt, groupby, drop, rename, etc
    - numpy, math, time
    
    
- **Data visualization**:
    - matplotlib: line charts, ordered bar charts, stacked bar charts, pie charts
    - basemap: for geographical visualization
    - plotly: for interactive graphs and animation (bubble charts)
    - ipywidgets and python decorator: for interactive graphs
    
    
- **Modelling**:
    - sklearn: for modelling




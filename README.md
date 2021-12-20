**Note: The main notebook we are using is [bus_ridership_project.ipynb](https://github.com/MUSA-550-Fall-2021/final-project-city-hall-llc/blob/main/bus_ridership_project.ipynb)**. <br /> The main notebook also uses this [LEHD Origin-Destination Employment Statistics (LODES) dataset](https://lehd.ces.census.gov/data/lodes/LODES7/il/od/il_od_main_JT00_2019.csv.gz) which is too large to be uploaded to GitHub. <br />Other notebooks in this repository are used for panel dashboards. 

# Bus Ridership Analysis and Prediction

CTA has 1,864 buses that make about 19,237 trips a day and serve 10,768 bus stops, according to the latest official tally in 2017. However, there is not much publicly available information on how the bus service has been used. What are the areas with lots of ridership? Are there any interesting spatial patterns? Are there areas with potential ridership demand, but are not accessible to a bus stop? This questions are even more important for cities without easily-accessible ridership data.

Through our project, we hope to gain a better understanding of the bus ridership service and usage and apply our insights to improve planning of bus stations. With Chicago's data, we will find boarding and alighting patterns across geographies and sociodemographics to select indicators of ridership demand. From there, we will build a prediction model to help predict ridership demand and demonstrate a use case on another city without ridership information. For our project we select Philadelphia. Finally, we will visualize a dashboard to help city officials identify areas in need of better bus services in the city.

This project acts as a preliminary proof-of-concept for the use of ridership prediction model in allocation bus services rather than a ready-to-use planning tool. We will discuss the limitations and next steps for transportation planners to build on in the future for the possibility of a more comprehensive and more useful tool.

## Analysis
Our analysis is consisted of several parts: data preparation, data exploration, regression and prediction, use case scenario, and conclusion. While we provide a summary here, please see our jupyter notebook for the detailed analysis.

### Data preparation
For this project we need data to support our model building and use case discussion. We collected a month-long [ridership data](https://data.cityofchicago.org/Transportation/CTA-Ridership-Avg-Weekday-Bus-Stop-Boardings-in-Oc/mq3i-nnqe) in 2012 from OpenDataChicago, socioeconomic data from census' 2015-2019 American Community Survey, and spatial features from OpenStreetMap at the block-group level. We wanted to use have the geographic level as small as possible to inform useful planning decision. We also collected socioeconomic data and spatial features data for Philadelphia.

### Data exploration
We used visuals to further understand the characteristics of our ridership, socioeconomi, and spatial data. First, we ploted the histogram to examine the distribution of our plausible explanatory variable. This had been turned into a dashboard as we think it would be helpful for city officials and planners to engage with the data easily in a dashboard. Next, we performed k-means clustering and depicted the clusters spatially. This had also been turned into a dashboard as dashboard enables users to engage with the clustering and understand them better. Then we made a correlation plot to illustrate the correlation among our variables.

### Regression and prediction
In model building, we trained and tested on Chicago and then predicted the model on Philadelphia. We considered both linear regression and random forest. Our model performed fair on the training set but not so well on the testing set. This is understandable as bus ridership is associated with very complicated features and a future step would be to collect better variables for model building. 

### Use case scenario
Finally, we built a dashboard to show the predicted demand and existing bus stations for Philadelphia, as a city without publicly available ridership data. An advantage of this is that the planners can allocate bus services base on demand instead of what are already there. This may help planners to identify areas that have been overlooked in the previous planning process and also areas that have been overserved with current bus system.

### Conclusion 
In this project, we explored the characteristics associated with demand for bus service and built a model in the hope to help city officials allocate bus services based on ridership demand. Despite our effort, limitations exists. If we have more time, a next step would be perfecting the model. However, such models should be used with caution because bus ridership is a very complicated topic that is related with funding, equity, and social welfare. Each service change should be decided with thoughtful investigations and also engagement with the community.



## Data Visualization Dashboards
As mentioned above, we built dashboards for planners and city officials to better engage with data when making bus service improvement decisions. Here are the dashboards.

### Dashboard 1: [Explorer of Socioeconomic Features (Chicago)](https://mybinder.org/v2/gh/MUSA-550-Fall-2021/final-project-city-hall-llc/HEAD?urlpath=%2Fpanel%2FSocioeconomic_Features_Explorer)
This link leads to the binder app for the histogram distribution of selected socioeconomic variables. Users can select variables from the dropdown box on the left. The plot on the right will help visualize the distribution of variables, which further could use to determine if data transformation is necessary. 

### Dashboard 2: Clustering Analysis (Chicago)
#### [Cluster Analysis of Chicago Bus System - Scatterplot View](https://mybinder.org/v2/gh/MUSA-550-Fall-2021/final-project-city-hall-llc/HEAD?urlpath=%2Fpanel%2FK-Mean_Clustering)
This link leads to the binder app for the K-Means Clustering dashboard. On this dashboard page, users can adjust the x and y variables to see the scatter plot for selected variables. 

#### [Cluster Analysis of Chicago Bus System - Map View](https://mybinder.org/v2/gh/MUSA-550-Fall-2021/final-project-city-hall-llc/HEAD?urlpath=%2Fpanel%2Fcluster_analysis_panel)
This link leads to the binder app for Cluster Analysis of Chicago Bus Ridership. On this dashboard page, users are able to adjust the number of clusters (2-8). The histogram shows how many observations in each clusters, and the map on the right shows the spatial distribution of the clusters.   


### Dashboard 3: Ridership Demand and Stops (Philadelphia) 
***Note: Since this one has large data size, it will experience a time out issue and so the url doesn't work. Please run through the notebook in order to see this app.***
This is a binder app for predicted Philadelphia bus ridership at block groups level. On this dashboard page, users are able to see the number of stops in an area with predicted ridership or other socioeconomics variables.

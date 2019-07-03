This was a part of the Capstone project at UBC in colloboration with the Centre for Population Health Data at [Statistics Canada](https://www.statcan.gc.ca/eng/start)

Our goal was to create a website/dashboard that is based on a given food and nutrition thematic data model. This data model contains five main categories: Food Supply, Distribution, Consumption, Utilization, Health Outcomes. The first step of the entire process is to categorize data products (data sets, publications, surveys) into the appropriate categories by building a text classification model. This repository contains the majority of code for data collection, text classification and plotly dashboards used in the website. 

[The Website Link](https://statisticcanada.github.io/)


Inside the dataset folder contains the [Training Data](https://github.com/statisticCanada/Project/tree/master/Datasets/Training%20Data), [New Data (To be Classified)](https://github.com/statisticCanada/Project/tree/master/Datasets/New%20Data%20(To%20be%20Classified)), as well as [Classified New Data](https://github.com/statisticCanada/Project/tree/master/Datasets/Classified%20New%20Data)

* Note: All data is saved in a csv file for easy python implementation

Training Data: 
* `Combined_Links.csv` contains the 417 record data set that we have manually categorized. This data set would act as our training data for all the text classifiers used in the notebooks. The columns contain: Title, Description, Link, Category, Subcategory, Source 

New data (To be classified): 
* `New Data.csv` Data set that has been scrapped and not labeled, we be categorized using the ensemble classifiers.

Classified New Data: 
* contains the categorized data set using the New data mentioned above.`combined.csv` uses the method of merging the all the predicted class of the base classifiers and dropped its duplicates. This method is not recommened and just used for or own research purposes. 

* The `Bestcombined.csv` is the best ensemble classifier classified data set. Contains 1376 records in total, 1033 in supply, 152 in consumption, 88 in Health Outcome, 44 in Distribution, and 59 in Utilization. The data set was examined for accuracy, we've realized that the 1033 supply category had some minor errors. It is categorizing data products that essentially is supply such as GDP, imports and exports, but not relevant to Food and Nutrition. This may be improved in the future. 


The code folder contains most of our code for our classifiers and web scraper
* [Classifier](https://github.com/statisticCanada/Project/tree/master/Code/Classifier)
  * contains all the code for the classifier
* [Webscraper](https://github.com/statisticCanada/Project/tree/master/Code/Webscrapper)
  * contains the webscraper notebook using `BeautifulSoup`
* [Visualizations](https://github.com/statisticCanada/Project/tree/master/Code/Webscrapper)
  * contains the ploty dash code used to build summary statistic visualizations

Note: Please insert mapbox access token for geolocation plots, this could simply be setting up a mapbox account. 

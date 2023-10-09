# EDABasics

![image](https://github.com/rxshmi-p/EDABasics/assets/86248667/966dc278-3f7b-44d7-9f30-1b8e4a4c86ad)


Exploratory data analysis, EDA for short, is an initial experimental process to learn useful information and formulate questions 
about a population based on an associated dataset. Some main priorities are examining the data, and preparing it for visualization, 
experimentation or modeling.

In order to further explain the topic of exploratory data analysis, we created a Jupyter Notebook that contains a code demonstration. In this notebook we go into a detailed example about the various steps included in the EDA process, using an example dataset of YouTube data.

## Data Exploration 
In this stage we aim to understand what the data looks like. In order to examine the dataset at a high level we first needed to import the necessary libraries and load our example dataset into a Pandas data frame.

Some useful libraries for data processing and storage include:
- Pandas
- Numpy

Some useful libraries for data visualization include: 
- Seaborn
- Matplotlib

To get a high level overview of the data, we first viewed the first few rows of the dataset using df.head(). This gives us a better understanding of the various features in the dataset as well as what to expect in terms of data types and normal values. From this point we used a variety of functions to get a better understanding of the overall shape of the data as well as the various data types for each feature. This information helped us to determine any initial outliers and data types that may be inaccurate.

<img width="1120" alt="Screen Shot 2023-10-08 at 9 10 05 PM" src="https://github.com/rxshmi-p/EDABasics/assets/86248667/0c0e767d-2ea0-4fb0-86e0-db7f043d47b7">

Once we had a general overview, we were able to select a target feature to investigate. For this demo, we selected the "Number of Likes" feature. In order to better understand this attribute, we plotted a histogram of the column values and identified that there were some very large outliers, but the vast majority of the values were clustered together.

![image](https://github.com/rxshmi-p/EDABasics/assets/86248667/0cc5bdc6-0a67-4535-a505-0bc9fda63692)






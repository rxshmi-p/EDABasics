# EDABasics

<p align="center">
  <img src="https://github.com/rxshmi-p/EDABasics/assets/86248667/966dc278-3f7b-44d7-9f30-1b8e4a4c86ad" width="480">
</p>

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

<p align="center">
  <img src="https://github.com/rxshmi-p/EDABasics/assets/86248667/0cd42e80-7f46-4bad-903a-278d7bbe6c37" width="480">
</p>

Once we had a general overview, we were able to select a target feature to investigate. For this demo, we selected the "Number of Likes" feature. In order to better understand this attribute, we plotted a histogram of the column values and identified that there were some very large outliers, but the vast majority of the values were clustered together.


![image](https://github.com/rxshmi-p/EDABasics/assets/86248667/a110f548-75c4-4ce8-907d-6ad760d91774)

## Data Cleaning 
Next we check for any weird columns that might need some preprocessing. For example, the column "Subtitles" has the uniques as shown below. 

<img width="361" alt="Screen Shot 2023-10-08 at 9 21 38 PM" src="https://github.com/rxshmi-p/EDABasics/assets/86248667/c8c48898-b678-4433-8217-5476e65ba314">

Since uppercase Yes and lowercase yes have the same meaning, we can change all values to be lowercase. As well we can make an assumption that a nan response is the same as a No. After making these changes we now only have two response categories. 

Next we handle any missing values with the process of imputation. Using the .isna() function we are able to see if any missing values exist in any columns and get their sums using .sum() 

<img width="361" alt="Screen Shot 2023-10-08 at 9 24 53 PM" src="https://github.com/rxshmi-p/EDABasics/assets/86248667/4951b9ed-5684-4ce9-bbe5-64ae5a55a683">

An interesting discovery in this stage was that the significant number of missing values in the Creator Gender column can be traced back to the fact that those videos were posted by a company, which has no gender. To handle these missing values, we can create a third column in Creator Gender, called Company. This is easily done using the .fillna() function. 

<img width="576" alt="Screen Shot 2023-10-08 at 9 28 32 PM" src="https://github.com/rxshmi-p/EDABasics/assets/86248667/ffbd0d90-a8d0-46f2-a573-478e61f5d4c3">

After this we are also able to change any column types to categorical or numeric as needed using pd.Categorical or pd.to_numeric. 

<img width="637" alt="Screen Shot 2023-10-08 at 9 29 48 PM" src="https://github.com/rxshmi-p/EDABasics/assets/86248667/96f477ec-b0c3-46d7-a908-9320f069f222">

## Data Visualization 
Now that the data has been cleaned, it is ready for visualization. To gain insights into the relationships between various features in the dataset, the use of plots can be highly beneficial. Here are some plots that we generated to delve deeper into the data:

Scatter Plot (Subscribers vs. Likes):

![image](https://github.com/rxshmi-p/EDABasics/assets/86248667/b490b88b-c88e-4c95-985a-d3092df98aa2)

Chosen Plot: Scatter plot was selected to explore the relationship between the number of subscribers and the number of likes. This was done using matplotlib.pyplot.scatter()

Purpose: It illustrates whether there’s a correlation or pattern between these two variables; higher subscribers might lead to more likes.



2. Bar Chart (Hashtags vs. Average Likes):

![image](https://github.com/rxshmi-p/EDABasics/assets/86248667/cc0f224c-8d75-4fdf-9f17-61c05e5a7b39)

- Chosen Plot: Bar chart was used to display the average number of likes for different numbers of hashtags. This was done using matplotlib.pyplot.bar()

- Purpose: It shows whether the use of hashtags has an impact on the average likes; higher bars indicate potentially higher engagement for certain hashtag counts.


## Conclusion 
These were the steps we chose to begin understanding this data better. However, EDA is an experimental process that is highly flexible and meant for individual understanding. As such, we could continue this process as much as we felt needed. Some areas we would look into further include:
- Outlier Removal: Identifying and removing outliers is crucial to improve data visualization and analysis accuracy.
- Date-Time Features: Analyzing features like release dates and last comment dates can reveal how time affects video likes.
- Text Features: Examining video titles and descriptions with NLP techniques can uncover factors influencing viewer engagement.


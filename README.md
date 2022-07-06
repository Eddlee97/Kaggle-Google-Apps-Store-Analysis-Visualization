# Kaggle Google Apps Store Analysis & Visualization
- Class: CIS 9650 Programming for Analytics (Python)

## Project Overview:
The goal of this project is to perform statistical analysis and create data visualization on Google Apps Store, then load them into a database.

***Data Source:*** <br>
https://www.kaggle.com/datasets/gauthamp10/google-playstore-apps

***Data Cleansing Process:*** <br>
Cleansed the dataset based on Price column using z-scores <br>
1. Calculated standard deviation and mean on Price column for all Paid apps <br>
2. If z-score for app was greater than 4 standard deviations, we removed paid app due to its price being an outlier. 296 rows were removed <br>
3. Dataset was already formatted properly (i.e. dates, uppercase) <br>
4. Dropped unnecessary columns ('app_id', 'minimum_android', 'developer_id', 'developer_website', 'developer_email', 'privacy_policy', 'ad_supported', 'in_app_purchases', 'editors_choice') <br>
5. Created two new dataframes, Paid apps and Free apps

***Rating Comparison:*** <br>
- If Rating is positive, Paid apps have a higher average rating compare to Free
- Paid apps have a higher rating in 29 categories
- Free apps have a higher rating in 19 categories
- Largest difference in favor of Paid apps:
  - Category: Libraries & Demo (0.98)
- Largest difference in favor of Free apps:
  - Category: Dating (-1.01)

![Alt text](https://github.com/Eddlee97/Kaggle-Google-Apps-Store-Analysis-Visualization/blob/ab0b566312b72c59e2660a6a09677ff270f2dcfc/Data%20Visualization/Apps%20Rating%20Diff%20(Free%20vs%20Paid).png)

***Statistical Analysis Summary:*** <br>
For the statistical analyses, we wanted to look for any outliers and calculate what the threshold was while focusing on the price and rating columns; furthermore we wanted to calculate the standard deviation and the mean of the price column for all paid apps. After that, we assigned a z-score for each row to determine if an app has a z-score that is greater than 4 standard deviations. The apps that meet this criteria were considered outliers and were removed from the dataset. 

## Data Visualization
![Alt text](https://github.com/Eddlee97/Kaggle-Google-Apps-Store-Analysis-Visualization/blob/d4aa3d873ce5c322f146b293adffe360bb036eb1/Data%20Visualization/Average%20app%20price%20by%20category.png)
This bar chart displays the number of installed apps in each category utilizing a for loop to loop through the cleaned dataset on “App Name”, “Category”, and “Maximum Installs” columns to identify the category that has the highest number of installs.  We applied a max function in the for loop to perform an iteration for each row grouping by category. We calculated a division by one million for each row in the “Maximum Installs” column using million as a unit so that the dataset is more comprehensible. Then, we implemented a sort function to organize from highest to lowest installs. From this analysis, we found that the highest install category is “Tools – Google Play service” with more than 12000+ million installs while the lowest is “Events – Ticketmaster” with only 14+ million installs.

![Alt text](https://github.com/Eddlee97/Kaggle-Google-Apps-Store-Analysis-Visualization/blob/d4aa3d873ce5c322f146b293adffe360bb036eb1/Data%20Visualization/App%20installs%20by%20category.png)
This bar chart shows the average app prices between each category incorporating groupby, mean, and sort functions. We found that the two highest average app prices come from the medical and business categories. 

## Insights Found:
These insights can help stock analysts who are looking to invest in companies based on their app downloads, to determine any correlation to a company's annual revenue, ad campaign, and more. Also, to help android users determine which app category has the most or least amount of installs and apps with good ratings with reasonable price tag. There are several ideas to expand the analysis of our project. 

## Possible Further Analysis:
We could further analyze how each app category compares to one another, which app categories hold the most success in attracting users, providing weighted rating information and further analysis on app purchase information.

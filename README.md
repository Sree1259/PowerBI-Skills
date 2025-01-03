# Power BI Exploratory Data Analysis (EDA) - Airbnb Dataset

## Overview
This repository highlights my skills in **Power BI** by performing **Exploratory Data Analysis (EDA)** on an Airbnb dataset. Using descriptive statistics and data visualization techniques, I identified patterns, relationships, and insights to enhance data-driven decision-making.

## Airbnb Dataset
The dataset includes the following attributes:
- **listing_id**: Unique identifier for listings[ex: apartments, houses, etc]  
- **host_id**: Unique identifier for hosts  
- **host_since_datekey**: Date the host joined Airbnb  
- **host_response_rate**: Host's response rate percentage  
- **host_acceptance_rate**: Host's acceptance rate percentage  
- **host_is_superhost**: Whether the host is a superhost (True/False)  
- **host_total_listings_count**: Total number of listings by the host  
- **neighbourhood**: Location of the listing  
- **city**: City where the listing is located  
- **latitude, longitude**: Geographical coordinates of the listing  
- **property_type**: Type of property (e.g., apartment, house)  
- **accommodates**: Number of people the property accommodates  
- **bedrooms**: Number of bedrooms  
- **price**: Price of the listing  
- **review_scores_rating**: Overall review score of the listing  
- **instant_bookable**: Whether the listing is instantly bookable (True/False)  
- **listing_size_sqft**: Size of the property in square feet  

---

## Exploratory Data Analysis (EDA)
EDA is a method of analyzing datasets to summarize their main characteristics using statistical and graphical techniques.

### 6 Steps of EDA:
#### 1. **Understanding the Data Structure**
- Identified data types, rows, and columns.  
- Differentiated **continuous variables** (e.g., price, review scores) from **categorical variables** (e.g., property type, city).  

#### 2. **Addressing Missing Data**
- **Removed rows and columns** with excessive missing data.  
- **Imputed missing values** using statistical techniques like median and mean for continuous variables.  

#### 3. **Describing Data**
- Used **descriptive statistics** (mean, median, standard deviation) for initial insights.  
- Visualized data distribution through **histograms** and **box plots**.  

#### 4. **Identifying Outliers**
- Calculated percentiles and IQR (Interquartile Range) to detect outliers.  
- Adjusted outliers in **review_scores_rating** using:
  ```DAX
  Modified_ratings = IF(airbnb[review_score_rating] < PERCENTILE.INC(airbnb[review_score_rating], 0.05), 
                        airbnb[review_score_rating], 
                        PERCENTILE.INC(airbnb[review_score_rating], 0.95))
  ```

#### 5. **Examining Relationships Between Variables**
- Discovered relationships between variables (categorical and continuous) using **scatter plots** and **box plots**.  
- Identified correlations to determine significant predictors.

#### 6. **Forming Hypotheses**
- Developed and tested hypotheses based on observed patterns.  

---

## Visualizations
Power BI visualizations include:
1. **Categorical Values visualization on listing_id by city and instance booking**
   
   <img width="586" alt="image" src="https://github.com/user-attachments/assets/b6d2dc4d-f434-4523-9996-23fcfcc56167" />
 - **Sydney and Rome**: Around 70% of listings have high instant booking rates, indicating a strong preference for instant booking in these cities.
 - **New York and Paris**: Around 40% of listings show high instant booking rates, suggesting a lower preference for instant booking compared to Sydney and Rome.
   
2. **Distribution in Review Scores with outliers**

   <img width="487" alt="image" src="https://github.com/user-attachments/assets/99870158-74e7-43e5-85e2-ae3451c04f56" />
 
3. **Analysis of Listing Price vs. Listing ID with City Distribution and Correlation Insights**
   
   <img width="589" alt="image" src="https://github.com/user-attachments/assets/10055c78-0bbe-4cc3-b04b-16dc22cd36b1" />
 - ***Sydney***: Sum of listing IDs is 2.2M; some listings have low square roots but high prices (outliers or premium listings).
- ***New York***: Many listing IDs near 0, with minimum square root values and prices; sum of listing IDs is 1.8M.
- ***Rome and Paris***: Few listings, with a trend of either high or low values for both listing ID square roots and prices, indicating market segmentation.
4. **City-wise Acceptance Rate Comparison**
  <img width="538" alt="image" src="https://github.com/user-attachments/assets/8e27541a-db7b-4401-80c1-65c8549b67bd" />
  
- **New York and Sydney**: Both cities have high acceptance rates, with values near the 0.7 mean, reflecting stronger acceptance in their respective listings.
- **Rome and Paris**: These cities show lower acceptance rates, with values near the 0.4 mean, indicating weaker acceptance in comparison to New York and Sydney.


## Tools and Techniques
- **Power BI** for data modeling and visualization.  
- **DAX** (Data Analysis Expressions) for data transformation.  
- Statistical measures to summarize data.  

---

## Learnings and Insights
- EDA is crucial for understanding data and making informed decisions.  
- Power BI's ability to combine statistical measures with visual storytelling enhances analysis effectiveness.  

  ## **Key Insights**:
- **Sydney and Rome**: High instant booking rates (~70%) and strong listing engagement, with premium listings showing distinct price patterns.
- **New York and Paris**: Lower instant booking rates (~40%) and market segmentation in listing prices and ID square roots.
- **Market Trends**: Sydney and Rome show higher market engagement, while New York and Paris reflect more varied listing patterns, suggesting diverse market dynamics across   cities.  
- **Data Insights**: The analysis highlights the importance of city-specific strategies for pricing and booking preferences.
---
### Credits:
Datacamp Exploratory Data Analysis in PowerBI Certification.

**Link for the Course:** https://www.datacamp.com/courses/exploratory-data-analysis-in-power-bi

### Final Thoughts
This project allowed me to gain hands-on experience with Power BI, enhancing my data visualization and analysis skills. Analyzing the data, I uncovered key insights such as the strong market engagement in Sydney and New York, and the lower acceptance rates in Rome and Paris. This experience strengthened my technical abilities and reinforced the importance of using data-driven insights to make informed decisions. It was a valuable opportunity to apply my analytical skills and deepen my understanding of Power BI as a powerful tool in data analysis.

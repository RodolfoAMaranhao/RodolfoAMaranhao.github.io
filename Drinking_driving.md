## Revealing Patterns in High Schoolers' Behavior: EDA and ML for Predicting and Preventing Riding with Drinking Drivers

**Project description:** In this project we will analyze the risk of high schoolers riding with drinking drivers by examining a dataset from the Youth Risk Behavior Surveillance System (YRBSS) in the U.S. Using Exploratory Data Analysis and Machine learning, we should identify factors contributing to this behavior and use the insights gained to develop preventive measures.

### 1. Import and Clean data 

We saould first import the data and perform some basic data cleaning steps, like getting dropping unwanted columns/null values and renaming columns so that they are more readable. 

```python
# Drop the first column that served as an index before
df = df.drop('Unnamed: 0', axis=1)

# Drop null values
df.dropna(inplace=True)

# Rename remaining columns
df.rename(columns={'age4': 'Age'}, inplace=True)
df.rename(columns={'female': 'Gender'}, inplace=True)
df.rename(columns={'grade': 'Grade'}, inplace=True)
df.rename(columns={'smoke': 'Smoker'}, inplace=True)
df.rename(columns={'ride.alc.driver': 'DrunkDriver'}, inplace=True)
```

### 2. EDA (exploratory data analysis)

now we can analyze the distribution of our data per feature, and then take a look at some overlaid plots to see if we can identify some potential differences between the high schoolers that ride with drinking drivers vs the ones that don't.



By taking a first look at our data we can definitely see some trends: <br><br>


<img src="images/OverlaidHistGender.png"/>
<img src="images/OverlaidHistSmoker.png"/>

• The female students seem to ride more often with drinking drivers <br><br>
• Smokers also seem to ride more frequently with drinking drivers <br><br>
• Grade, Age and Having a Driver's License did not seem to exhibit a different pattern between the passengers of drinking drivers <br><br>


### 3. Feature Engineering



```python

```

### 4. Create Machine Learning Models



<img src="images/ML Models Results.png"/>
<img src="images/ML Models ROC AUC.png"/>

### 5. Conclusion, actionable steps and project limitations

• Popular songs tend to have higher energy, be less explicit and last between 2 to 6 minutes.  <br><br>


To 

For more details see <a href="https://github.com/RodolfoAMaranhao/Predicting-Song-Popularity-on-Spotify">Project Files</a> 


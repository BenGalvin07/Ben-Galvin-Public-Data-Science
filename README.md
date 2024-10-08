

# Electric Vehicle Battery Sizes and Driving Distance

## Introduction
The reason why I was interested in understanding the battery size/capacity and the range in KM is because I purchased my first electric vehicle in 2023 but did no prior research into batter sizes and what this would mean in terms of drivable distance as a result, I purchased a car, that was excellent to drive, cheap to charge but was unable to do a long distance drive without having to stop multiple times, using expensive public charging locations. Using the knowledge and skills learnt during my Data Science degree, I am now able to analyse data from the EV car market and make a more details and informed choice of what car to purchase next time.

## Data Collection
The data that was used for the analysis of this project was downloaded from Kaggle. The Dataset [Cheapest Electric Cars 2023](https://www.kaggle.com/datasets/kkhandekar/cheapest-electric-cars)

**Pre Clean Dataset**

The data was downloaded in the format that can be seen in the image below. There was excess data in columns that wouldnt be required for this peice of analysis. 

<img src="assets/ExcelPreCleanDataSetcopy.JPG" width="600">

**Columns to be Removed**

The columns highlighted in green would remain in the final clean cut of data. The data in the columns highlighted in Red/Orange would be removed. 

<img src="assets/Columnstodelete.JPG" width="600">

**Missing Data**

<img src="assets/FastChargingData.JPG" width="600">

Within one column of data, the fast charging column two rows of data were missing, to ensure the data was complete, the manufacturers website was consulted to obtain the missing information. As the two vehicles do you use fast charging, there will be no data and therefore the information is replaced with dashes.


**Data Manipulation**
The column tiles were manipulated to ensure the information was ready for analysis in Power BI and Excel. 
The following adjustments were made:
- Column titles to be named clearly with units of measurement inside (kWh and kms)
- Data editing to remove the km from the Range km Column as the title had the units of measurements
- Removal of excess characters in column Useable Battery kWh as this would prevent analysis. The excess characters were removed by a LEN function and Find and Replace

The different stages of the manipulation can be found in the below images:
<img src="assets/ColumnManip1.JPG" width="600">

<img src="assets/DataManipulation2.JPG" width="600">

<img src="assets/DataManip3.JPG" width="600">

<img src="assets/DataManip4Len.JPG" width="600">


## Data Analysis

**Data Analysis - Excel**

The data from the Usable Battery kWh and Range KM to create the data points for the linear regression. the X Axis will be the Battery Size kWh and the Y Axis will be the Range KM, the below screenshot shows the items being selected for the regression analysis. 

<img src="assets/1ExcelRegressionSelection.JPG" width="600">

The next step was to format the X & Y axis to ensure they were titled correctly, also had to ensure the legend was labled correctly. A Linear trend line was also added

<img src="assets/2ExcelRegression Data.JPG" width="600">

The results are shownn in the next two screenshots and will be discussed in the results section

<img src="assets/4NewExcelData.JPG" width="500"> <img src="assets/3SummaryOutput.JPG" width="300">

**Data Analysis - Power BI**

The data was also input into Power BI to create some visuals and a small dashboard to give an details of the EV with the highest range in KM and the EV with the shortest range in KM

The data was loaded directly from One Drive using the Excel get data function

<img src="assets/01Dataload.JPG" width="500"> <img src="assets/02Datalocation.jpg" width="400">

The data was then transformed into the correct data types becuase power BI didnt recognise the data in the Useable Battery kWh column. it was corrected to Decimal Number. The screenshot show the before transformation and after

<img src="assets/03datatransformation.JPG" width="500"> <img src="assets/04Datatypeselection.JPG" width="500"> 

A scatter plot was created to show the Values of the cars when hovered over in the values column, with the X Axis being the Useable Battery and the Y Axis being the Range KM. 

<img src="assets/05DataandViz.JPG" width="300">

Finally a Trend line and average lines were added to the final scatter plot to create the Linear regression chart

<img src="assets/06TrendLine.JPG" width="500"> <img src="assets/07CrossLines.JPG" width="500">

For a little bit of fun, a card was added to show the longest and shortest range EVs in the dataset, along with the filters used to create them

<img src="assets/08MaxRange.JPG" width="500"> 
<img src="assets/09MinRange.JPG" width="500">

## Results

The analysis conducted on the relationship between the EV battery capacity and the size of their usable battery demonstrates a strong positive correlation between the two. Using linear regression, the results indicate that as the battery capacity increases, the range available to the vehicle also increases.
The multiple R value of 0.89 suggests a very strong positive correlation between the variables, indicating that the model’s predictions are closely aligned with the actual data. The R-squared value of 0.79 indicates that approximately 79% of the variance in the EV range can be explained by the battery capacity alone.
This high R-squared value suggests that battery capacity is a reliable predictor of the range, though 21% of the variance is attributed to other factors not included in the model. This could include different outside factors which could influence the range, such as weight, the design, and the driving conditions when the range was calculated.
The findings demonstrate the importance of battery capacity in determining the usability and practicality of electric vehicles. To answer the question, does a useable battery size on an Electric Car (EV) result in longer range in KMs? Would be a positive yes, more usable battery would indicate more useable range.

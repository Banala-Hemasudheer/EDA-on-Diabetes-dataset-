# Exploratory Data Analysis on Diabetes Dataset

### Table of contents
[1. Introduction](#introduction)
  * [Aim](#aim)
  * [Dataset](#dataset)

[2. Basic Exploration](#basic-exploration)
  * [Examining distributions of the data ](#examining-distributions-of-the-data)
  
[3. Dealing with missing values](#dealing-with-missing-values)
  * [Comparision of advance imputation techniques](#comparision-of-advance-imputation-techniques)

[4. EDA](#eda)
  * [Conclusion](#conclusion)


<!-- toc -->

# Introduction

Changes in the life style of people due to urbanization and several other factors leads to the increase in the number of diabetes patients. This disease is a challenge to the health care sector as it's difficult to cure a patient completely, if once he got affected.

Major factors associated with the diabetes are:

1) Are overweight.
2) Are 45 years or older. Have a parent, brother, or sister with type 2 diabetes.
3) Are physically active less than 3 times a week.
4) Have ever had gestational diabetes (diabetes during pregnancy) or given birth to a baby who weighed over 9 pounds.

## Aim 
**To find the major factors associated with the diabetes in women with the help of EDA.**

### Dataset
This dataset comes from the National Institute of Diabetes and Digestive and Kidney Diseases.

**Variables used in the dataset:**


1) Pregnancies: Number of times pregnant.

2) Glucose: Plasma glucose concentration 2 hours in an oral glucose tolerance test. (155 mg/dL or lower - normal, otherwise - prediabetes).

3) Blood Pressure: Diastolic blood pressure (mm Hg) (60 to 80 - normal, otherwise - Hypotension and Hypertension).

4) Skin Thickness: Triceps skin fold thickness (mm) (Average value is 23.6 ± 7.5 mm for women).

5) Insulin: 2-Hour serum insulin (mu U/ml) ( 16-166 mIU/L or mu U/ml is considered normal ).

6) BMI: Body mass index (weight in kg/(height in m)^2) (< 18.5 Underweight, 18.5—24.9 Healthy Weight, 25.0—29.9 Overweight, > 30.0 Obesity).

7) Diabetes Pedigree Function: Diabetes pedigree function (indicates the function which scores likelihood of diabetes based on family history).

8) Age: Age (years).

Outcome: Class variable (0 or 1) 0 mean non-diabetic and 1 means diabetic.

# Basic Exploration
![image](https://user-images.githubusercontent.com/111430368/220256910-79dddebb-8dae-4e98-97ac-733d5554f82f.png)

![image](https://user-images.githubusercontent.com/111430368/220258517-514e12ea-7add-425a-968f-29bf09667456.png)

## Examining distributions of the data

![image](https://user-images.githubusercontent.com/111430368/220257458-596f2088-fe88-4e4e-8ab7-8f0b78b0e1de.png)

![image](https://user-images.githubusercontent.com/111430368/220257594-3c4dbac4-2d1e-4b03-a0c6-019f4af701a3.png)

**Observation:** 
We can find Glucose, Blood Pressure , Skin Thickness(Tricep skin fold thickness), Insulin, BMI, as 0 which is not possible. Must Treat them as missing values

# Dealing with missing values
The percentage of missing values in all the columns are as follows:

![image](https://user-images.githubusercontent.com/111430368/220260523-2df102b1-99fb-4c7e-912a-d8657708fea3.png)

Insulin column is having very high amount of missing values. Insulin in blood test is sometimes used along with other tests to help diagnose and monitor type 1 diabetes. Hence, it's dropped.

Few other columns are having vey low amount of missing values, so the rows corresponding to these missing values are dropped.

## Comparision of advance imputation techniques
The advance imputation is performed on the skin thickness column. Advance imputation techniques like SWA, MICE, SoftImpute were used.

![image](https://user-images.githubusercontent.com/111430368/220261876-18ea42f3-8620-437c-8a4d-b1aab03e6755.png)

**Observation** : MICE Imputation seems to be better imputation technique for the given data.

# EDA

**Aim**: To check whether more number of pregnancies will cause diabetes.

![image](https://user-images.githubusercontent.com/111430368/220263029-be7c9002-ee0b-4b42-b06a-49d2a896a841.png)

**Observation**:

1) Increase in weight resulting increase in diabetic cases.
2) Women with pregnancies more than 2 and having more weight are more prone to be diabetic.


**Aim**: To check the relation between glucose levels and diabetes.

![image](https://user-images.githubusercontent.com/111430368/220263498-54ae8557-be19-40c0-8428-a1100b3e986c.png)

**Observation**: Diabetic people are having higher glucose levels compared to non - diabetic.
(155 mg/dL or lower - normal, otherwise - prediabetes)

**Aim**: To check relation between blood pressure and diabetes.

![image](https://user-images.githubusercontent.com/111430368/220263861-b0390ee9-a555-4ebc-9345-fadf1251c9a1.png)

**Observation**: Obese people are having abnormal BP values compared to remaining. Diabetic people are having slightly higher BP than non diabetic.

Blood Pressure: Diastolic blood pressure (mm Hg) (60 to 80 - normal, otherwise - hypotension, Hypertension)

**Aim**: To check the relation between skin thickness and diabetes

![image](https://user-images.githubusercontent.com/111430368/220264118-fffdb043-0b99-4891-9733-f314ddd693b4.png)

**Observation**: People are more prone to diabetes when there's increase in skin thickness and BMI.

![image](https://user-images.githubusercontent.com/111430368/220264424-3e3c9a6f-e29c-46b6-8358-0451d7483140.png)

**Observation**:

1) People are more prone to diabetes when there's increase in skin thickness and BMI with glucose greater than normal level (155).
2) Linear relationship between skin thickness and BMI

Skin Thickness: Triceps skin fold thickness (mm) (Average value is 23.6 ± 7.5 mm for women)

**Aim**: To find the relationship between BMI and outcome

![image](https://user-images.githubusercontent.com/111430368/220264730-6ab95a18-aaab-4e5c-8b5f-c998ba690b79.png)

**Observation**: In the given dataset ( Non-diabetic - 497, Diabetic - 266 ). Here more number of diabetic people fall under category Obese.

**Aim**: To find the relationship between Diabetes pedigree function and outcome

![image](https://user-images.githubusercontent.com/111430368/220265001-061fb256-a1b1-4a53-9203-6042f2808219.png)

**Observation**: Diabetes pedigree function (indicates the function which scores likelihood of diabetes based on family history) values are higher for diabetic people.

**Aim**: To find relation between age and outcome

![image](https://user-images.githubusercontent.com/111430368/220265237-51588af6-7502-4785-879e-b2d9f9941864.png)

**Observation** :In the given data, more diabetic people were found to be Young adults (age<40 )

# Conclusion

1) women with over weight & pregnancies more than 2 are more prone to diabetic.
2) Few women (Non-Diabetic) were found with higher glucose levels. They are in prediabetes stage.
3) Diabetic & Obese women are having slightly higher & abnorml blood pressue values compared to non diabetic & healthy women.
4) Diabetic people were found more when they are having Obesity with Glucose greater than normal (150).
5) More number of diabetic people were found with age less than 40 and having Obesity.

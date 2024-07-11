# Highlighting Hospital Successes with SQL

![Healthcare Project Cover Art](hospital.png) <br><br>

Hospitals are a critical part of our healthcare infrastructure and one of the main providers of diabetic treatment for millions of people in the US. With rates of diabetes increasing amongst americans it is critical that hospitals are providing sufficient care in an efficient way. Clinical outcomes for diabetic patients have been improving, but only when appropriate care is provided. If hospitals are able to utilize the right treatments sooner, the likelihood of patient readmission decreases. This greatly reduces management and administration costs for the hosptital, while also improving morbidity and mortality rates among diabetic patients. <br>

To determine how well hospitals are doing I obtained patient data from 130 hospitals tracking clinical care of diabetic patients over the course of ten years. Each row of the data represents records of patients diagnosed with diabetes, who stayed in the hospital for up to 14 days while receiving care. The data shows the lenth of stay at the hospital, lab procedures performed, medications taken, and whether or not the patient was readmitted. There are 101,766 intances in the data with 71,518 distinct patient records. The original dataset can be found [here](https://www.kaggle.com/code/iabhishekofficial/prediction-on-hospital-readmission/notebook). <br>

Using SQL I was able to analyze this data and extract some key insights on the hospitals performance. Specifically I was asked to determine the following: <br>

- Are the majority of patients staying less than 7 days?
- What is the relationship between the number of lab procedures performed and the length of stay at the hospital?
- What are the medical specialties that are utilized the most?
- Is there any racial bias in treatment?
- Were there any patients that had a diabetic emergency, but were discharged from the hospital faster than average? <br>

Let's see what we were able to find.

## The Power of SQL: Analysis

SQL is not known for its data visualization capabilities. However, with the right SQL query we can create a basic histogram from the data. This is a great way to quickly find the answer to our first question. Are the majority of patients staying less than 7 days? Here are the results: <br>

#### Length of Stay SQL Histogram
![Histogram SQL Script](sqlhistogram.png)<br>
![Histogram Results](histogram.png)<br>

Using this special SQL script we can see that the vast majorits of patients are in the hospital for less than 7 days, so the hospitals in this dataset are doing great on that front. The RPAD function is the key to this histogram in SQL. RPAD creates a column with a sting value in each row. In this case we are using the COUNT() of patients to determine the lenth of the strings, and representing each patient with an '*' to have the strings represent bars in a histogram. I divided the counts by 100 because we are dealing with a lot of patients. This shortens the bars so that we could see the full histogram on one page. Of the 101,766 instances in this dataset, 80,617 of those resulted in a hospital stay of less than 7 days. <br><br>


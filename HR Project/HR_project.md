# Analyzing HR Data with R

![Statistical Analysis with R](HR.png) <br><br>

Human Resources are the most valuable resources for any business. It is important to find ways to attract employees that fit are a good fit for the company and role they are performing, and to create an environment that keeps those employees motivated and content at the company. In this data analysis I used R, a powerful statistical analysis language, to gain insights from an IBM HR dataset to try to determine why employee attrition at IBM was increasing.

#### The IBM Dataset
For this project I am taking on the role of an IBM People Data Analyst intern. Recently there have been many employees leaving the company and IBM leadership wants to know why. This dataset was created by IBM data scientists but is a fictional dataset. The data contains 1,470 rows each representing an employee, and there ar 35 columns tracking different attributes that describe these employees. The "Attrition" column will be the most important attribute for this project as this tells us whether or not the employee stayed at IBM. There are some columns that contain demographic data such as age, education, and marital status. Other columns contain job-related data like monthly income, years at the company, and some categorical numbers for things like performance rating and work-life balance. I was asked to determine the following:

- Are there any signficant correlations between the most important attributes?
- What trends can be seen between these correlated attributes?
- Is there any evidence of ageism in attrition rates?
- Were employees just randomly selected for firing?
- How much do factors like age, monthly income, work-life balance, and distance from home affect the chances of an employee leaving the company?

Let's see what insights we can gain from this data using R.

## Statistical Analysis with R

First, I wanted to find out if there are any correlations between the most important attributes in this dataset. IBM determined that age, daily rate, distance from home, education, hourly rate, monthly income, monthly rate, number of companies worked at, total working eyars, and training times last year are significant variables they want to track. But, before I determine relationships between these attributes I needed to read the data into RStudio to create a dataframe.

![Read a CSV file](read_csv.png) <br>

Now that I have the dataframe created I can run the correlation matrix for the important attributes using the "cor" function in R. See the results below:

![Correlation Matrix Code](corr_matrix.png)<br>
![Correlation Matrix Results](r_corr_matrix.png)<br>

Based on these results I determined that there were significant relationships between Age and Monthly Income, Total Working Years, and Education. To learn more about these relationships I wanted to see the data. A great way to get a quick picture of these relationships is to create a pairplot in R.

![Pairplot Code](r_pairplot.png)<br>
![Pairplot Results](r_pairplot_pic.png)<br>

I can see a few things that stand out in this data visualization. Interestingly, education level does not appear to have a big impact on monthly income, and age is not as big a factor in education as one might expect. Education in this dataset is a categorical numerical value with "1" meaning below college level education, and "5" meaning doctorate level. In these plots I can see multiple employees with doctorate-level education making less than $5,000 per month. I can also see examples of employees in their late 20s and early 30s with doctorates. <br>

There does appear to be a clear threshold when comparing monthly income with total working years. This plot shows a clear line where employees with over 20 total working years are making at least $5,000 per month. <br>

Finally, I see that age does have a positive correlation with monthly income, but again, this is not as pronounced as I expected. While there are no employees under 20 making more than $5,000 per month, employees aged 25 and above have monthly incomes covering the full range of possible values. This is an interesting group of employees! <br><br>





# The World Bank Analysis <br>
<img src="The World Bank.png?raw=true"/> <br>

Living in the United States we don't often think about international development. But I feel that there is a good case to be made for aiding other countries in their development to help all people enjoy the things we do in the United States. The International Development Association (IDA) does just that. As part of The World Bank the IDA extends credits, grants, and guarentees to its member countries to help them acheive their goals. <br><br>
How much money does the IDA grant to its members? Who is the biggest recipient of these funds? What are these funds being used for? I decided to run some SQL queries on the IDA's Statement of Credits and Grants to find out. <br><br>

### Here's What I Found <br>
- The IDA has a total of 1,304,781 transactions
- The total value due to the IDA in USD is $23,801,874,654,808.31, wow!
- The highest amount due to the IDA totals $1,047,501,691.07 and transaction was issued to Ukraine
- The lowest value transaction is with Mozambique valued at -$5.37
- India holds the most transactions with 66,711
- There are 6,162 transactions dedicated to the Project Name "Education II"
- The average service charge rate is 0.79% with the highest rate being 7.09% and the lowest being .075%
<br><br>

### Dataset Details <br>
This dataset comes directly from The World Bank and the latest IDA Statement of Credits and Grants can be found [here.](https://finances.worldbank.org/Loans-and-Credits/IDA-Statement-Of-Credits-and-Grants-Historical-Dat/tdwh-3krx/about_data) The data contains 1,304,781 rows representing transactions with 138 distinct countries. The report captures many attributes, but the key attributes include Country, Region, Amount Due to the IDA, Amount Disbursed by the IDA, and Amount Repaid to the IDA, Service Charge Rate, and Credit Status. The data further classifies transactions by Project Name, various transaction dates, and any 3rd parties involved. This is a massive dataset, so let's try to make some sense of it.
<br><br>

### My Analysis Using SQL Queries <br>
To get an overview of this data I needed to see how many rows we're dealing with, and what attributes are being collected. By using a simple Count query I discovered that our report has 1,304,781 rows. I then performed a Select all query to see all the attributes (columns) in the dataset. Because we are working with so much data I had to limit these results to 500 rows. See the queries and results below: <br>

#### Count All Rows <br>
![Count Query](wb_count.png) <br>
![Count Results](wb_countallpic.png) <br>
#### Select All Columns <br>
![Select Query](wb_selectall.png) <br>
![Select Results](wb_selectallpic.png) <br><br>

Next, I wanted to see what the total amount due to the IDA was. To do this we need to aggregate all the transations with a Select query, and SUM function. Here's the outcome: <br>
#### Sum of All Transactions <br>
![Sum Query](wb_sum2.png) <br>
![Sum Results](wb_sumpic.png) <br>

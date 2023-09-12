Sales Insights - Data Analysis using Tableau & SQL tableau
I am sharing India based Hardware company Sales Insights - A Data Analysis Project performed on Tableau & SQL in my journey into Data Science.

For more detials, refer: Data Analyst Roadmap ⌛

About Project 👨‍💻
Performed India based hardware company sales insights - A Data Analysis project.

Developed ETL mappings using SQL to extract the data from unstructured data and transformed it to the staging area to conduct data cleaning and design star schema data model on Tableau.

Developed a Tableau dashboard to perform analysis, producing quantitative visualizations in Tableau to draw valuable insights based on different parameters affecting the company performance year on year and further provide business solutions.

Technologies used ⚙️
Advance Excel excel

MySQL mysql | SQL Server sql-server

Tableau tableau | Power BI powerbi

Statistics 
Problem Statements
Sales director wants to know the performance of the company in various Indian states & accordingly provide some discount.

Q1. Revenue breakdown by cities.

Q2. Revenue brekdown by years & months.

Q3. Top 5 customers by revenue & sales quantity.

Q4. Top 5 Products by revenue.

Q5. Net Profit & Profit Margin by Market

Approach - Project Planning & Aims Grid
1. Purpose: What? Why? What do we want to achieve?
To unlock sales insights that are not visible before for sales team for decision support & automate them to reduced manual time spent in data gathering.

2. Stake Holders: Who will be involved?
Sales Director,
I.T. Team,
Customer Service Team,
Data & Analytics Team.
3. End Result: What do we want to achieve?
An automated dashboard providing quick & latest sales insights in order to support data driven decision making.

4. Success Criteria: What will be our success criteria?
Dashboards uncovering sales order insights with latest data available.
Sales team able to take better decision & prove 10% cost savings of total spend.
Sales analysts stop data gathering manually in order to save 20% of their business time & reinvest it in value added activity
Data Analysis - Approach


Setup Process
Step 1: Download file: db_dump.sql or db_dump.xlsx

Step 2: Import it in MySql do ETL(Extract, Transform, Load) if required

Step 3: Download Tableau Public (Free) or Tableau Desktop (14 days trial) to perform Data Analysis

Step 4: Connect Tableau with MySql database or Excel database

Step 5: Save the file as (.twb or .twbx)

Data Analysis Using SQL
Show all customer records

SELECT * FROM customers;

Show total number of customers

SELECT count(*) FROM customers;

Show transactions for Chennai market (market code for chennai is Mark001)

SELECT * FROM transactions where market_code='Mark001';

Show distrinct product codes that were sold in chennai.

SELECT distinct product_code FROM transactions where market_code='Mark001';

Show transactions where currency is US dollars.

SELECT * from transactions where currency="USD"

Show transactions in 2020 join by date table.

SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

Show total revenue in year 2020.

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";

Show total revenue in year 2020, January Month.

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");

Show total revenue in year 2020 in Chennai.

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020and transactions.market_code="Mark001";

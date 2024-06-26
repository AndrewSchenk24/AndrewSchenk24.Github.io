# World Bank Lending Analysis

Since 1947, the World Bank has funded over 12,000 development projects, via low interest loans, grants, and other forms of financial assistance. Many of these projects involve developing infrastructure, education, and social programs in developing countries. The World Bank serves as a vital resource for many countries for both financial and technical support for long term development and in response to critical events such as recovery from natural disasters. Through its focus on economic development and reduction of poverty, the World Bank has affected the lives of millions of people in its member countries. 

### The Scenario

I have been tasked by the World Bank to **analyze their most recent data to give an update on current lending**. Specifically, I have been tasked with providing an update on the following questions:
 
- **How many countries are receiving assistance** from the World Bank and through **how many projects**?
- How many projects and associated loans are being supported **in each member country**? 
- What is the **total amount currently owed** to the World Bank by all countries?
- What is the **average service charge** for loans that are still in repayment?
- Who are the 10 countries with the **greatest amount of outstanding debt**?
- What **types of projects** are most highly financed?

### The Results

- The World Bank is currently serving **127 countries funding 7450 different projects**
- **India, Bangladesh, and Pakistan** lead the way in total number of projects supported by the World Bank
- Current total due to the World Bank is over **198 billion dollars**
- For loans that are currently in repayment, the **average service charge is just 0.95%**
- The **top 10 countries** with the greatest amount due to the World Bank account for 126 billion or **64% of all money due**.
- The term **"Growth"** appears in the project name of 3 of the projects most highly financed by the World Bank

### The Analysis

This project was completed in SQL by using basic commands including **aggregate functions** and **GROUP BY** statements, **aliases**, filtering with **WHERE** statements, and sorting with **ORDER BY** statements. **LIMIT** statements were also used to select specific outcomes.

The Data for this project was collected directly from the World Bank website is the **most recent snapshot** reflecting the current status of loans as of January 16, 2024. The data set contains over ten-thousand rows of data, each row representing an individual loan, with 30 characteristics or columns for each loan.  The dataset can be found [here](https://finances.worldbank.org/Loans-and-Credits/IDA-Statement-of-Credits-and-Grants-Latest-Availab/ebmi-69yj/about_data) if you’re interested in taking a look. 

The World Bank data was downloaded as a .CSV and uploaded to a table named **"bank_data"** for SQL analysis.

To accomplish the first task and determine the number of countries with outstanding loans we can use SQL to **COUNT the different countries** that have loans listed in the data set. Since **"Project ID" is used to identify a specific project** this column can be used to identify the number of projects currently supported by the World Bank. 
<br/><br/>
<img src="images/SQL Project Query 1.png?raw=true"/>
<img src="images/SQL Project Result 1.png?raw=true"/>
<br/><br/>
This first query gives some summary information. As of January 16, 2024 the **World bank is supporting 7450 different projects in 127 of its member countries**. To breakdown this information further we can use a **GROUP BY clause to see how many projects and loans are attributed to each country**. By using an **ORDER BY clause to sort the returned data** the countries with the highest number of loans and highest number of projects can be identified.

<img src="images/SQL Project Query 2.png?raw=true"/>
<img src="images/SQL Project Result 2.png?raw=true"/>

An interesting insight from this breakdown of projects and loans by country is that **any singular project may be funded by multiple loans**. This query also informs the World bank on which countries receive the most support, based on sheer number of projects, with India, Bangladesh and Pakistan leading the way.

From here the next task is to look at **some basic financial characteristics of outstanding loans** due to the World Bank and to calculate the average interest rate being charged to member countries for that financing. Calculating total amount owed to the World Bank can be found by **adding the amount due from each loan**. When calculating the average interest rate for outstanding loans a **WHERE** clause is used to **filter only those loans that are still currently in repayment**. By using this filter we are sure to calculate the average interest rates just on loans in repayment and exclude loan interest rates from loans that have been fully repaid.
<br/><br/>

<img src="images/SQL Project Query 3.png?raw=true"/>
<img src="images/SQL Project Result 3a.png?raw=true"/>
<img src="images/SQL Project Query 4.png?raw=true"/>
<img src="images/SQL Project Result 4a.png?raw=true"/>

We find that the World Bank has **over 198 billion currently invested in its member countries** and has provided financing with, on average, an **interest rate below one percent**. These numbers speak to the willingness of the World Bank to fulfil its mission to provide low interest financing to help its member countries.

Now that we have an idea of total amount due across all member countries, the next query is designed to identify the 10 countries that have the most oustanding debt by **examining total amount due to the World Bank by country**.

<img src="images/SQL Project Query 5.png?raw=true"/>
<img src="images/SQL Project Result 5b.png?raw=true"/>

The top three countries that we learned have the greatest number of projects funded by the World Bank **(Bangladesh, India, and Pakistan) predictably also owe the greatest amounts to the World Bank**. With a total of 126 billion owed, these **10 member countries account for 64% of all amounts due** to the World Bank and as such receive the greatest amount of aid from the World Bank.

The focus now shifts to the last task of identifying the **individual projects that have the most outstanding debt**. Since each project may have multiple loans it's necessary to **add all amounts due for all loans connected to an individual project**. By using a **SUM** function and **GROUP BY "Project Name"** this calculation can be made.  

<img src="images/SQL Project Query 6a.png?raw=true"/>
<img src="images/SQL Project Result 6a.png?raw=true"/>

The results of this query speak to the wide array of projects, services, and support that the World Bank provides to its member countries. Some of the **largest investments in individual projects** are related to creating economic stability, infrastructure improvement, peace efforts, educational improvement, and providing support for the poor. **Growth is a frequent theme** in many of the most highly funded projects and is indicative that the World Bank is continuing to focus on its mission to **"end extreme poverty and boost prosperity on a livable planet."**
<br/><br/>

I hope that you enjoyed learning about the World Bank and exploring its most recent lending snapshot by harnessing the power of SQL. I appreciate your time, am always learning and improving, and would love to hear any input or recommendations you have regarding this article and analysis. Let's connect on [LinkedIn](https://www.linkedin.com/in/andrewschenk-pt-mba/)!








# Current World Bank Lending

Since 1947, the World Bank has funded over 12,000 development projects, via low interest loans, grants, and other forms of financial assistance. Many of these projects involve developing infrastructure, education, and social programs in developing countries. The World Bank serves as a vital resource for many countries for both financial and technical support for long term development and in response to critical events such as recovery from natural disasters. Through its focus on economic development and reduction of poverty, the World Bank has affected the lives of millions of people in its member countries. 

### The Scenario

I have been tasked by the World Bank to analyze their most recent data to give an update on current lending. Specifically, I have been tasked with providing an update on the following questions:
 
- How many countries are receiving assistance from the World Bank and through how many projects?
- How many projects and associated loans are being supported in member countries? 
- What is the total amount currently owed to the World Bank by all countries?
- What is the average service charge for loans that are still in repayment?
- Who are the 10 countries with the greatest amount of outstanding debt?
- What types of projects are most highly financed?

### The Results

- The World Bank is currently serving 127 countries funding 7450 different projects
- India, Bangladesh, and Pakistan lead the way in total number of projects supported by the World Bank
- Current total due to the World Bank is over 198 billion dollars
- For loans that are currently in repayment, the average service charge is just 0.95%
- The top 10 countries with the greatest amount due to the World Bank account for 123 billion or 62% of all money due.
- The term "Growth" appears in the project name of 3 of the projects most highly financed by the World Bank

### The Analysis

This project was completed in SQL by using basic commands including aggregate functions and GROUP by statements, aliases, filtering with WHERE statements, and sorting with ORDER BY statements. LIMIT staements were also used to select specific outcomes.

The Data for this project was collected directly from the World Bank website is the most recent snapshot reflecting the current status of loans as of January 16, 2024. The data set contains over ten-thousand rows of data, each row representing an individual loan, with 30 characteristics or columns for each loan.  The dataset can be found [here](https://finances.worldbank.org/Loans-and-Credits/IDA-Statement-of-Credits-and-Grants-Latest-Availab/ebmi-69yj/about_data) if you’re interested in taking a look. 

The World Bank data was downloaded as a .CSV and uploaded and named "bank_data" for the project

To determine the number of countries with outstanding loans we can use SQL to COUNT the different countries that have loans listed in the data set. Since "Project ID" is used to identify a specific project this column can be used to identify the number of projects currently supported by the World Bank. 
<br/><br/>
<img src="images/SQL Project Query 1.png?raw=true"/>
<br/><br/>
This query calculated and pulled the following results:
<br/><br/>
<img src="images/SQL Project Result 1.png?raw=true"/>


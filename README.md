# Case Study 1: Credit - Exploratory Data Analysis

--------------------------------------------------------------------------
--------------------------------------------------------------------------

This was an assignment I completed as a part of my Post Graduate Diploma in Data Science from Upgrad & IIIT-Bangalore. The dataset and the Problem Statement was provided to me by Upgrad.


**Group Size - 2**


The datasets were provided by Upgrad:
- application_data.csv - https://drive.google.com/file/d/1qIiR2nDPv9QemqbtupwyRQnk2ASvIBjT/view?usp=sharing
- previous_application.csv - https://drive.google.com/file/d/1hnIzTIJfyc1DW9q9wp2iua61wiUXmivK/view?usp=sharing
- column_description.csv - https://drive.google.com/file/d/1LVmSWLdOPdUyaUHNe7LYo__eNoIzzAgZ/view?usp=sharing


`The report that follows is my explanation of what was performed in the Case Study.`

--------------------------------------------------------

## Business Understanding:
----------------------------
The loan providing companies find it hard to give loans to the people due to their insufficient or non-existent credit history. Because of that, some consumers use it as their advantage by becoming a defaulter. Suppose you work for a consumer finance company which specialises in lending various types of loans to urban customers. The banks goal should be to ensure that the applicants capable of repaying the loan are not rejected.

When the company receives a loan application, the company has to decide for loan approval based on the applicant’s profile. Two types of risks are associated with the bank’s decision:
- If the applicant is likely to repay the loan, then not approving the loan results in a loss of business to the company
- If the applicant is not likely to repay the loan, i.e. he/she is likely to default, then approving the loan may lead to a financial loss for the company.

The data given below contains the information about the loan application at the time of applying for the loan. It contains two types of scenarios:
- The client with payment difficulties: he/she had late payment more than X days on at least one of the first Y instalments of the loan in our sample,
- All other cases: All other cases when the payment is paid on time.

When a client applies for a loan, there are four types of decisions that could be taken by the client/company):

- `Approved`: 	The Company has approved loan Application
- `Cancelled`: 	The client cancelled the application sometime during approval. Either the client changed her/his mind about the loan or in some cases due to a higher risk of the client he received worse pricing which he did not want.
- `Refused`: 	The company had rejected the loan (because the client does not meet their requirements etc.).
- `Unused offer`:  	Loan has been cancelled by the client but on different stages of the process.

--------------------------------------------------------

## Business Objectives & Problem Statement:
------------------------
This case study aims to identify patterns which indicate if a client has difficulty paying their installments which may be used for taking actions such as denying the loan, reducing the amount of loan, lending (too risky applicants) at a higher interest rate, etc. This will ensure that the consumers capable of repaying the loan are not rejected.<br>
In other words, the company wants to understand the driving factors (or driver variables) behind loan default, i.e. the variables which are strong indicators of default. The company can utilize this knowledge for its portfolio and risk assessment.<br>
We will make the use of Exploratory Data Analysis to identify such applicants.<br>

--------------------------------------------------------

## Data Understanding:
-------------------------
This dataset has 3 files as explained below: 
- `application_data.csv`: Contains all the information of the client at the time of application. The data is about whether a client has payment difficulties.
- `previous_application.csv`: Contains information about the client’s previous loan data. It contains the data whether the previous application had been Approved, Cancelled, Refused or Unused offer.
- `columns_description.csv`: This is a **data dictionary** which describes the meaning of the variables.


There were two main datasets that we deal with -
- ***application_data***
- ***previous_application***

We initially analyze the application_data dataset and then we will merge the previous_application dataset to the application_data and continue with the analysis. The methodology for the datasets is as follows:

--------------------------------------------------------

## Methodology
-------------------------
- 1) Reading & Understanding the Data

- 2) Data Cleaning & Preparation
	- Removing unnecessary columns.
	- Dealing with Null values (visible & non-visible).
	- Deriving various Metrics

- 3) Univariate Analysis
	- Outlier Analysis
	- Univariate Analysis of Continuous columns
	- Univariate Analysis of Numerical columns

- 4) Bivariate Analysis & Multivariate Analysis
	- Correlation Analysis

--------------------------------------------------------

### Observations and Inferences from the Data
--------------------------------------------

#### Observation & Inferences from Univariate Analysis

- We observed that the inter-quartile range of clients WHO HAVE DEFAULTED is slightly higher than clients WHO HAVE NOT DEFAULTED. We also observed that number of outliers for DEFAULTER clients is more and high as compared to clients who are NOT Defaulters. 
- We see that the interquartile range for the credit amount data is higher for clients WHO ARE defaulters. We see that outliers are present in both cases, but for Targer = 0, outliers are more on the higher side.
- We can infer that clients who are seeking a higher credit loan amount tend to deefault more as compared to clients who take a lower credit loan amount.
<br><br>
- We see that for Loan Annuity, both types (i.e. Defaulters and Non-Defaulters) follow a similar trend of values, with Non-Defaulters having a slighlty higher Inter-Quartile range.
- We see that clients with the income in range of 100 thousand to 150 thousand have the most number of Defaults.
- The clients in the segment are in the count of 80,000+
- We can infer that most defaulters are middle class people, in the salary range of 75 thousand to 250 thousand dollars.
- We can also infer that the clients that have very low salary or very high salary less likely to default.
<br><br>
- We can observe the majority of the values lie between 100 thousand dollars to 500 thousand dollars.
- We can also observe that there are clients who have very high incomes, but are still loan defaulters.
- We observe that people below the age of 25 and people above the age og 65 are less likely to default. This can be so because people in the above age range are very less likely to take loans.
- The age segment of 25 to 65 all have nearly the same number of defaulters.
- We can infer that age is not a very strong indicator of clients being defaulters.
<br><br>
- We also observed that that number of non-defaulters follows decreases with age. We also observed that people in the age range of 20-25 are more likely to be non-defaulters. We can infer that people in age range of above 65 are less likely to take loans.
- We see that people who Deafult the most have either taken a very high loan, i.e. in the range of 900 thousand and above, OR have taken a loan in the range of 200 thousand to 300 thousand.
<br><br>
- From the box plot of Credit Dispersion of Clients who HAVE Defaulted, we can observe that 75% of clients who have defauler have taken a loan amount in the range of 45 thousand dollars and 81 thousand dollars. 
- Apart from that quite a few outliers are present in the distribution. From this it can be inferred that, there might have been some clients, who tool a huge loan to start a business, but have defaulted due to their business faulure or similar problems.
- The number of clients who HAVE NOT defaulted follow a simliar pattern for their credit amount range as compared to the clients who HAVE defaulted.
<br><br>
- We observe that the working class clients have the highest frequency of defaulters.
- We also observe that clients who are unemployed, students, businessman and clients who are on maternity leave have a low chance of defaulting. We can infer that these clients have less probability of taking loans.
- We can also infer State Servents are comparitively less likely to Default, since they have a safe and regular salary.
<br><br>
- We observe that married people are more likely to default.
- We also observe that people who are widow or widower are less likely to default.
- We observe that people who took cash loans are more likely to default as compared to revolving loans.
- We can clearly see that number of clients with only a secondary education have a very high probability to default as compared to a client who has completed his/her higher education.
- From the above observation, we can infer the clients with higher with higher level of education might be earning weill and may be less susceptible to be a defaulter.
- We observe that clients who work in a business entity are more likely to take loans and default.
- Another category of clients which are highly susceptible to Default are self-employed people.


### Observation & Inferences from Bivariate & Multivariate Analysis

Comparing the pairplots of clients with payment difficulties and all other cases, we observe:
- The clients having low income are more likely to default. 
- There seem to be no defaulters having a higher income.
- The more is the goods price, the higher credit is available in both the cases.
- In the case of default, a very high credit is not available even if the price of goods is high while in all other cases a higher credit may be available in case of a high goods price.
<br><br>
- There are no cases of default in the case of students and businessman.
- The proportion of females in case of all income types is higher as compared to males in case of all other cases than in case of default.
<br><br>
- A large number of applications are by people having secondary education followed Higher Education both in the case of payment difficulties and all other cases.
- Female applicants are more than male applicants in all cases.
<br><br>
-The proportion of no-default by females is higher than males in case of cash loans when compared with default.
<br><br>
- With the increase in age, there is a decreasing trend of applications in all cases.
- The females are less likely to default from the ages 25 to 65 while the possibility of default is decreasing with increase in age.
- Overall, the age group of 25 to 45 is less likely to default.
<br><br>
- The Office apartment which are not owned by the client have a higher default as compared to the office apartment owned by client.
- The default possibility is less in the case the Co-op Apartments not owned by client as compared to all other cases.
<br><br>
- The median credit amount is the highest in case of married person having an academic degree.
- The credit maount of people in civil marriage having an academic degree are mostly in the third quartile.
- The education type 'Academic Degree' has the least outliers, which means there is not much variability in the credit amount of this category.


### Observations & Inferences from the Correlation Heatmaps of the variables

- We find that the highest correlation exists between Credit Amount and the Goods Price. We can infer that the loan amount must be taken to buy the goods.

- We also find a very high correlation between Credt Amount and Loan Annuity Amount.

- We can also observe a high correlation between days after birth and the days after starting work.

- There is also a high correlation between LIVE_REGION_NOT_WORK_REGION and REG_REGION_NOT_WORK_REGION. It can be inferred that there is a high probability where a person who did not mention his/her permanent address as work address will not have mentioned his/her contact address as work address.

- There is also a high correlation between LIVE_CITY_NOT_WORK_CITY and REG_CITY_NOT_WORK_CITY. It can be inferred that there is a high probabilit where a person who did not mention his/her permanent address as work address will not have mentioned his/her contact address as work address.

- Credit Amount and Age show negative correlation. It can be inferred that credit amount is higher for low age and vice-versa.

- There is a negative correlation between Region_population_Relative and CNT_CHILDREN. It can be inferred that clients with less chilren live in densely populated areas.

- We observe a positive correlation between Credit amount and Region_Population_Relative. We can infer that people living in densely populated region take higher amount loans.

- We also observe a positive correlation between clients income amount and Region_Population_Relative. It can be inferred that clients living in densely populated region have a higher income.


### Observations & Inferences from the Merging the previous datasets to the application dataset

- We see that the clients who in the past are repeaters are more susceptible to Default on their loans. Majority of them have contract status as Refused.
- We also see that Number of Defaulter clients in the category - 'New' have contract type - 'Refused' are far more than clients in the same category and having contract type - 'Unused Offer'
- We also see a near similar trend follows for non-defaulters as well.
<br><br>
- We can observe that most number of defaulters clients are taking loans for Goods categories - 'Mobile', followed by 'Computers' and 'Audio Video Equipment'.
- We see that most of the Defaulters as well as the Non-Defaulters have majority of their contract status as - 'Refused'.
- We also find that clients associated with 'Fitness' as their Goods Cateogry are very less susceptible to Default on their loans

--------------------------------------------------------

## Conclusion
--------------------------------
There are some variables which are greatly impacting the chances of a client being a Loan Defaulter.
They include -

- 1) --> Client's Total Income
- 2) --> Credit Amount: Total Credit Amount taken by the Client as Loan
- 3) --> Income Type of Client
- 4) --> Family Status of the Client
- 5) --> Education Level of the Client
- 6) --> Type of client: (whether a client is a Repeater or a New client or a Refreshed client)
- 7) --> Goods_Categories: Goods for which the loan is taken.

--------------------------------------------------------

## Business Insights
----------------------------
> - `Bank should check the profile of a client thoroughly, who have income in the brackett of 100 thousand dollars and 250 thousand dollars, before granting them loan.`
<br><br>
> - `Bank should also check the profile of a client thoroughly, who are taking a loan either in the brackett of 200 to 300 thousand dollars or in the range 900 thousand dollars and above.`
<br><br>
> - `Working class clients should be thoroughly processed, since they are the majority loan seekers and have a high probability to default.`
<br><br>
> - `Well educated clients (Education level of Higher Education) should be granted more loans as compared to the less educated clients (Education level of Secondary/Secondary Special Education).`
<br><br>
> - `Clients seeking loan for buying goods like Mobile Phones, Computers and Audio/Video equipments should be processed thoroughly before being granted the loan.`
<br><br>
> - `Clients who are repeating loan seeker pose a high threat for Loan Default, so they should also be checked before being granted loan.`

--------------------------------------------------------
--------------------------------------------------------




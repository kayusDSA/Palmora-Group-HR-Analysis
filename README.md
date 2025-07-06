### Table of Content
1. Project TopicDescription
2. Project Overview
3. Data Source
4. Tool Used
5. Data Cleaning and Preparation
6. Exploratory Data Analysis
- Data Understanding
- Data Preparation
- Text Cleaning
7. Data Analyses  
i. What is the gender distribution in the organization? Distil to regions and departments
ii. Show insights on ratings based on gender
iii. Analyze the company’s salary structure. Identify if there is a gender pay gap. If there is, identify the department and regions that should be the focus of management
iv. A recent regulation was adopted which requires manufacturing companies to pay employees a minimum of $90,000.
- Does Palmoria meet this requirement?
- Show the pay distribution of employees grouped by a band of $10,000.
- How many employees fall into a band of $10,000 – $20,000, $20,000 – $30,000, etc.?
v. Also visualize this by regions
8. Findings of the Study
9. Recommendations
  
### Project Topic 
Bridging the Gap: A Gender Equality Analysis of The Palmoria Group’s Workforce 

### Description
The Palmoria Group, a Nigeria-based manufacturing company with operations across three regions, is currently facing intense public scrutiny over allegations of gender inequality. The controversy gained widespread attention following a media headline labelling the company “Palmoria, the Manufacturing Patriarchy.” This development poses a significant threat to the company’s long-term vision of regional and international expansion, as well as its corporate reputation. This study will address this issue in order to promote gender equality in Palmoria Group.

### Project Overview 
This project aims to help Palmoria proactively address internal gender inequalities, close any gender pay gaps, and build a more inclusive, equitable workplace culture in alignment with international best practices—thus safeguarding its brand and preparing it for responsible expansion.

### Data Source:
The Data Source used for this project is an CSV file, which is a secondary.

### Tools Used
Microsoft Power BI (For creating report). It can be [downloaded here](https://www.microsoft.com/en-us/download/details.aspx?id=58494)

### Data Cleaning and Preparation

![DATA OVERVIEW](https://github.com/user-attachments/assets/a55dfbcb-1e9d-45e0-bb8a-ebecbd6ebabb)

From the overview of datasets displayed above, it’s important and necessary we prepare the datasets before analysis and visualization is carried out.

### Exploratory Data Analysis

**Data Understanding**
A Microsoft Excel Worksheet (csv) dataset was provided for analysis consisting of 1016 rows and 6 columns.
The Palmoria Data workbook consist of the Name, Gender, Department, Salary, Location and Rating.

**Data Preparation**
The Power query tool in Power BI is used to get and transform data for appropriate analysis. Upon clicking Transform Data and navigating to power query window, I explored the data composition in order to know if any necessary data cleaning is needed by leveraging the Data Profiling Distributor feature which gives a summary of the column quality, distribution and profile.

**Text Cleaning**

**Gender Column**
One of the issues identified during the data cleaning process was with the “Gender” column. The column contains male, female and blanks. So, I replaced the blanks with Undisclosed. The power query replaced values was used. [See preview below;]

Gender Column Before Cleaning

![GENDER COL BF CLEANING](https://github.com/user-attachments/assets/41915077-d1d6-4c5a-85cd-22f8ffa166f2)

Gender Column contains blanks. There is an instruction from the company: there is a need to assign a generic gender status to these employees.
So, the employees without gender was given Undisclosed using Replace Values. See prewieve below:

![REPLACE VALUES](https://github.com/user-attachments/assets/52a681f4-e5e4-4844-ba7d-72f78d908f77)

![GENDER AFTER CLEANING](https://github.com/user-attachments/assets/ee8bb8db-e572-46a2-8554-f84aa23b4cd5)

**Salary Column**

Some employees are without salary because they are no longer with the company. Hence, these employees need to be taken out of the organization’s profile.

![SALARY BEFORE CLEANING](https://github.com/user-attachments/assets/837ec836-c1ea-40cc-b852-ac6a56937e4c)

These employees can be taken out of the organization’s profile thus: Highlight on the Salary column and click on filter icon and uncheck the NULL. The rows reduced to 946 [See preview below] 

![SALARY AFTER CLEANING](https://github.com/user-attachments/assets/70ee6d61-2882-4fc9-ac37-fb26114c5a8b)

**Department Column**

Some departments are indicated as “NULL”. These departments would also need to be taken out.
There are few rows that have a “NULL” text in the column. So, departments with NULL were removed by unchecking the NULL from the list of departments through filter. The rows reduced to 946 from 972 rows [See preview below] 

![DPT](https://github.com/user-attachments/assets/a4d2f00f-475d-44c4-b561-996a54a197d0)

### Data Analyses

In other to answer the key questions needed to make the business decisions, there is a need to analyze the data provided to gain insights which will then be visualized to effectively communicate to management of the Palmoria Group.

### 1.	What is the gender distribution in the organization? Distil to regions and departments

<img width="462" alt="GENDER BY DEPT AND REGION" src="https://github.com/user-attachments/assets/b81da9ec-abb5-47f4-a6a2-09dc6d755520" />

The dashboard above presents a clear breakdown of gender distribution across departments and locations (regions) in the organization.
This matrix shows how gender counts (not broken down by male/female, just total here) are distributed across:
Regions: Abuja, Kaduna, Lagos
Departments:
Human Resources: Largest in Lagos (15 more than Abuja), followed by Abuja and Kaduna
Product Management: Most populated in Abuja (40) compared to Kaduna (25) and Lagos (24)
Support and Business Development show fairly balanced distribution across all regions.

**Insight:**

Abuja seems to have a relatively higher representation across most departments.

Some departments (e.g., Legal, Product Management) may be regionally concentrated — worth exploring gender specifics here.

### 2. Show insights on ratings based on gender 

<img width="455" alt="RATING BY GENDER" src="https://github.com/user-attachments/assets/13e5f1c7-df89-42ca-8fff-426290cd3a5b" />
<img width="465" alt="GENDER BY RATING" src="https://github.com/user-attachments/assets/8fa4fcde-5b5e-4b20-a3cd-a85b7f7e00e2" />

The above viuals show insight on ratings based on gender. Statistics shows that the number, 212 of male employees are more rated on the average than the female employees at 190. The number of female employees who are rated good (89) are slightly higher than that of male employees at 89.
Moreover, the number of male employees who are rated poor (70) are more compared to female employees at 58.

### 3. Analyse the company’s salary structure. Identify if there is a gender pay gap. 
### If there is, identify the department and regions that should be the focus of management

**Gender Pay Gap Calculation:** 
To determine Gender Pay Gap, average salary measures for male and female within each comparable job role is calculate using **DAX FUNCTIONS**

a)	Employee Average Salaries: 
```
Average Salary = AVERAGE('HR ANALYSIS'[Salary])
```    
b)	Gender-Specific (Male and Female) Average Salary Measures:
```
Average Salary (Male) CALCULATE(AVERAGE('HR ANALYSIS'[Salary]), 'HR ANALYSIS'[Gender] = "Male"
```
```
Average Salary (Female) = CALCULATE(AVERAGE('HR ANALYSIS'[Salary]), 'HR  ANALYSIS'[Gender] = "Female")
```
c)	The Gender Pay Gap Percentage Calculation: 
This is calculated by subtracting the average salary of women from the average salary of men, and divide the result by the average salary of men. Multiply by 100 to express it as a percentage using NEW MEASURES as follows:

```
Gender Pay Gaps (%) = 'HR ANALYSIS'[Avg Salary (Female)]- 'HR ANALYSIS'[Avg Salary (Female)] / 'HR ANALYSIS'[Avg Salary (Male)] * 100
```
<img width="468" alt="GENDER PAY GAP" src="https://github.com/user-attachments/assets/ed0f26a2-9971-46e4-85da-3156f4f62d3b" />

<img width="536" alt="GENDER PAY GAP ABJ" src="https://github.com/user-attachments/assets/e12536c0-1e55-4a2b-b581-5f18de62d3bd" />

<img width="563" alt="GENDER PAY GAY K AND LAG" src="https://github.com/user-attachments/assets/72c5386c-79a4-4fce-969d-8e46c6e2d8dd" />

**Top Priority Areas for Management**
1.	Engineering Department (in all 3 regions)
- Gap ranges from 12.09% (Lagos) to 34.63% (Kaduna)
- Consistent and severe inequality
2.	Research & Development (Abuja and Lagos)
- Gaps over 19%
3.	Legal and Training (Abuja and Kaduna)
- Regular disparities that must be addressed
4.	Services and Business Development (Abuja & Kaduna)

### 4. A recent regulation was adopted which requires manufacturing companies to pay employees a minimum of $90,000 
### a) Does Palmoria meet this requirement? 

<img width="342" alt="SALARY BAND BY GENDER" src="https://github.com/user-attachments/assets/1ae149c6-ccec-4ade-a527-35804d1ad2ba" />

Based on the above visual "Salary Band by Gender", we can analyze whether The Palmoria Group meets the new regulation that requires a minimum salary of $90,000 for all employees

**Summary of Salary Distribution**
Out of a total of 946 employees, here is how many employees fall below $90,000:

<img width="467" alt="Q4" src="https://github.com/user-attachments/assets/8290f037-7084-475b-b945-5037d9eba7d0" />

The salary distribution shows that Palmoria does not meet the the new regulation requirement: Only 292 out of 946 employees (≈31%) earn at or above the $90,000 minimum threshold. This means approximately 69% of employees are currently underpaid according to the regulation.

### 4b. Show the pay distribution of employees grouped by a band of $10,000. For example: 
Data Analysis Expression (DAX) is used to create a salary band of $10,000 for the employees to know each employee's salary band. This is achieved by using the 'SWITCH COMMAND'.
The below is the Data Analysis Expression (DAX) used to create a salary band of $10,000 for the employees to know each employee's salary band and the employee's salary band using the 'SWITCH COMMAND'.
```
Salary Band = SWITCH(TRUE(), 'HR ANALYSIS'[Salary] < 10000, "<$10000",
    'HR ANALYSIS'[Salary] >= 10000 && 'HR ANALYSIS'[Salary] <= 20000, "$10000-$20000",
    'HR ANALYSIS'[Salary] > 20000 && 'HR ANALYSIS'[Salary] <= 30000, "$20000-$30000",
    'HR ANALYSIS'[Salary] > 30000 && 'HR ANALYSIS'[Salary] <= 40000, "$30000-$40000",
    'HR ANALYSIS'[Salary] > 40000 && 'HR ANALYSIS'[Salary] <= 50000, "$40000-$50000",
    'HR ANALYSIS'[Salary] > 50000 && 'HR ANALYSIS'[Salary] <= 60000, "$50000-$60000",
    'HR ANALYSIS'[Salary] > 60000 && 'HR ANALYSIS'[Salary] <= 70000, "$60000-$70000",
    'HR ANALYSIS'[Salary] > 70000 && 'HR ANALYSIS'[Salary] <= 80000, "$70000-$80000",
    'HR ANALYSIS'[Salary] > 80000 && 'HR ANALYSIS'[Salary] <= 90000, "$80000-$90000",
    'HR ANALYSIS'[Salary] > 90000 && 'HR ANALYSIS'[Salary] <= 100000, "$90000-$100000",
    'HR ANALYSIS'[Salary] > 100000 && 'HR ANALYSIS'[Salary] <= 110000, "$100000-$110000",
    'HR ANALYSIS'[Salary] > 110000 && 'HR ANALYSIS'[Salary] <= 120000, "$110000-$120000", BLANK())
```
![FULL SALARY BAND](https://github.com/user-attachments/assets/24817e6c-2a83-48ce-aa5d-c96cf87f58dc)

<img width="98" alt="SALARY BAND" src="https://github.com/user-attachments/assets/96187e2c-df4a-4ec2-907b-729c3e9de7f3" />

### 4c. How many employees fall into a band of $10,000 – $20,000, $20,000 – $30,000, etc.? 

<img width="342" alt="SALARY BAND BY GENDER" src="https://github.com/user-attachments/assets/1e56d0d9-039c-44cd-8d11-2218a1b68948" />

<img width="467" alt="Q4" src="https://github.com/user-attachments/assets/f76b9bc7-de38-4c48-b3a7-337cef74c9f6" />

Tables above shows the number of employees that fall into salary band.

### 4d. Also visualize this by regions 

<img width="347" alt="SALARY BAND BY REGION" src="https://github.com/user-attachments/assets/83b353ae-bb44-4e78-b4e5-876a9d5a641d" />

<img width="702" alt="DASHBOARD" src="https://github.com/user-attachments/assets/903590ce-d062-4fea-9d3f-5cbf94cfb5cc" />

### Findings of the Study

The study reveals that there is a Gender Imbalance. That is, gender distribution varies significantly across regions and departments:
A substantial underrepresentation of women in some technical departments like Engineering and R&D.

Also, there is a Gender Pay Gap: Significant disparities in average salaries between male and female employees. In other words,
There are top departments with gender pay gaps. Such as
Engineering: Worst affected (up to 34.63% gap in Kaduna).
Research & Development: Over 19% gap in Abuja and Lagos.
Legal and Training: High disparities in Abuja and Kaduna.
Services and Business Development: Gaps noticeable in Abuja and Kaduna.

Furthermore, study reveals minimum Wage Compliance Failure.
New regulation mandates a minimum salary of $90,000 for all employees in the manufacturing sector.
Only 292 out of 946 employees (~31%) meet this requirement.
69% of employees are underpaid, with many in the $20,000–$80,000 salary range.

On Salary Band Distribution, largest group of employees fall into $70,000–$80,000 and $80,000–$90,000 bands. while few employees are in the highest bands ($110,000–$120,000). 
There is also a clear salary clustering under the $90,000 mark — highlights structural compensation issues.

### Recommendations
1. Based on the findings of the study, the following recommendations are provided management’s attention.
- There is an urgent need to address Gender Pay Inequality across the regions and departemnts
- Conduct a detailed compensation audit across all roles and regions.
- Develop a pay equity policy and align compensation for equal roles across genders.

2. Prioritize these departments:
- Engineering
- R&D
- Legal & Training
- Business Development

3. Comply with Minimum Wage Regulation by
- Immediately review employees earning less than $90,000.
- Developing a phased salary upgrade plan to bring at least all full-time staff into compliance.
- Engaging finance to forecast impacts on the payroll budget.

4. Enhance Transparency
- Publish annual diversity and pay equity reports.
- Introduce salary bands and role leveling to ensure fairness.

5. Create a Gender-Inclusive Workplace
- Train HR and leadership on unconscious bias and inclusive hiring.
- Set department-level gender balance goals.
- Launch mentorship and career advancement programs targeted at underrepresented groups.




   

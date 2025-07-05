# Palmora-Group-HR-Analysis

### Description
The Palmoria Group, a Nigeria-based manufacturing company with operations across three regions, is currently facing intense public scrutiny over allegations of gender inequality. The controversy gained widespread attention following a media headline labelling the company “Palmoria, the Manufacturing Patriarchy.” This development poses a significant threat to the company’s long-term vision of regional and international expansion, as well as its corporate reputation. This study will address this issue in order to promote gender equality in Palmoria Group.

### Project Topic 
Bridging the Gap: A Gender Equality Analysis of The Palmoria Group’s Workforce

### Project Overview 
This project aims to help Palmoria proactively address internal gender inequalities, close any gender pay gaps, and build a more inclusive, equitable workplace culture in alignment with international best practices—thus safeguarding its brand and preparing it for responsible expansion.

### Data Source:
The Data Source used for this project is an CSV file, which is a secondary.

### Tools Used
Microsoft Power BI (For creating report). It can be [downloaded here](https://www.microsoft.com/en-us/download/details.aspx?id=58494)

### Data Cleaning and Preparation


From the overview of datasets displayed above, it’s important and necessary we prepare the datasets before analysis and visualization is carried out.

### Exploratory Data Analysis

**DATA UNDERSTANDING**
A Microsoft Excel Worksheet (csv) dataset was provided for analysis consisting of 1016 rows and 6 columns.
The Palmoria Data workbook consist of the Name, Gender, Department, Salary, Location and Rating.

**DATA PREPARATION**
The Power query tool in Power BI is used to get and transform data for appropriate analysis. Upon clicking Transform Data and navigating to power query window, I explored the data composition in order to know if any necessary data cleaning is needed by leveraging the Data Profiling Distributor feature which gives a summary of the column quality, distribution and profile.

### Text Cleaning:

**Gender Column**
One of the issues identified during the data cleaning process was with the “Gender” column. The column contains male, female and blanks. So, I replaced the blanks with Undisclosed. The power query replaced values was used. [See preview below;]

Gender Column Before Cleaning

Gender Column contains blanks. There is an instruction from the company: there is a need to assign a generic gender status to these employees.
So, the employees without gender was given Undisclosed using Replace Values. See prewieve below:


**Salary Column**

Some employees are without salary because they are no longer with the company. Hence, these employees need to be taken out of the organization’s profile.


These employees can be taken out of the organization’s profile thus: Highlight on the Salary column and click on filter icon and uncheck the NULL. The rows reduced to 946 [See preview below] 





**Department Column**

Some departments are indicated as “NULL”. These departments would also need to be taken out.
There are few rows that have a “NULL” text in the column. So, departments with NULL were removed by unchecking the NULL from the list of departments through filter. The rows reduced to 946 from 972 rows [See preview below] 



### Data Analysis

In other to answer the key questions needed to make the business decisions, there is a need to analyze the data provided to gain insights which will then be visualized to effectively communicate to management of the Palmoria Group.

### 1.	What is the gender distribution in the organization? Distil to regions and departments

Gender distribution across different regions in a Power BI dashboard, a clustered column chart or a 100% stacked column chart can be used

### 2. Show insights on ratings based on gender 


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
### 4. A recent regulation was adopted which requires manufacturing companies to pay employees a minimum of $90,000 
### a) Does Palmoria meet this requirement? 


Based on the above visual "Salary Band by Gender", we can analyze whether The Palmoria Group meets the new regulation that requires a minimum salary of $90,000 for all employees.


**Summary of Salary Distribution**
Out of a total of 946 employees, here is how many employees fall below $90,000:



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


### 4c. How many employees fall into a band of $10,000 – $20,000, $20,000 – $30,000, etc.? 



### 4d. Also visualize this by regions 






   

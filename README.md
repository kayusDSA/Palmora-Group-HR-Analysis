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


These employees can be taken out of the organization’s profile thus: Highlight on the Salary column and click on filter icon and uncheck the NULL. The rows reduced to 946 [See preview below;] 





**Department Column**
Some departments are indicated as “NULL”. These departments would also need to be taken out.
There are few rows that have a “NULL” text in the column. So, departments with NULL were removed by unchecking the NULL from the list of departments through filter. The rows reduced to 946 from 972 rows [See preview below;] 




### Data Analysis

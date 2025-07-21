# DSA-CAPSTONE-PROJECT-2

### PALMORIA GROUP HUMAN RESOURCE ANALYSIS

[Project Overview](project-overview)

[Objectives](objectives)

[Data Source](data-source)

[Data Description or Characteristics](data-description-or-characteristics)

[Tools Used](tools-used)

[Data Cleaning and Preparation](data-cleaning-and-preparation)

[Exploratory Data Analysis](exploratory-data-analysis)

[Data Analysis and Visualization](data-analysis-and-visualization)

[Data Interpretation or Analysis in Details](data-interpretation-or-analysis-in-details)

[Recommendations](recommendations)

[Summary](summary)

### Project Overview
---
The Palmoria Group is a manufacturing company based in Nigeria faced with issues concerning gender inequality in its regions.This project intend to help tackle this by providing a comprehensive data-driven overview of the Palmoria Group’s human resource distribution, performance, and compensation metrics across departments, regions, and gender classifications. It is aimed at equipping stakeholders with actionable insights to optimize workforce management and organizational strategy.

### Objectives
---
-To analyze gender balance across departments and regions
-To assess salary distribution and equity.
-To evaluate employee performance ratings.
-To understand regional workforce distribution and payroll implications.
-To provide insights that inform HR decisions and stakeholder strategies.

### Data Source
---
The Palmora Group HR Analysis dataset is an Excel file primarily sourced from DSA Data Analysis Capstone Project and this is an open source data which can be downloaded freely from an Open source online.

### Data Description or Characteristics
---
-Datasets
Raw Dataset (Palmoria Group emp-data.csv) [view](https://canvas.instructure.com/courses/11955369/files/folder/DSA%20Capstone%20Project%20Files?preview=302720549), (Palmoria Group Bonus Rules.xlsx) [view](https://canvas.instructure.com/courses/11955369/files/folder/DSA%20Capstone%20Project%20Files?preview=302720540).

1. The Palmoria Group emp-data: This contains the employees information about their name, gender, department, location and performance rating.
2. Palmoria Group Bonus Rules contains: This contains the company's bonus allocation criteria for the different departments based on the employees' performance ratings (Very Good, Good, Average, Poor and Very Poor).

### Tools Used
---
-Microsoft PowerBI Desktop [Download Here](https://www.microsoft.com/en-us/download/details.aspx?id=58494)
1. Data Cleaning
2. Data Analysis
3. Visualization
- Github for portfolio building
  
### Data Cleaning and Preparation
---
1. Data observation
   * Data Loadng
   * Blank Rows: It was observed that some employees refused to disclose their gender while some are without a salary because they are no longer with the company.
   * Unassigned values: Some departments returned as "NULL" while some employees were "NOT RATED" under the rating column; lacking the criteria for bonus allocation
   * Bonus Rule table had values for multiple ratings (Very Good, Good, Average, Poor and Very Poor) by corresponding departments.
2. Data Cleaning

   Upon loading of dataset, transformation was made in the following order:
   * Data Formatting: Ensure all texts, currency values, and percentages are formatted consistently.
   * Replacing Blanks Rows: Used "Edit Query" to replace blank values with "Unspecified" in the Gender column for workers who did not indicate their gender.
   * Removing Blanks Rows: Simply by unchecking "blanks" within the Salary column as those workers no longer work with the company in consideration.
   
### Exploratory Data Analysis
---
EDA involved the exploration of the data to answer some questions about the dataset such as:
1. What is the gender distribution in the organization? Distil to regions and departments
2. Show insights on ratings based on gender
3. Analyse the company’s salary structure. Identify if there is a gender pay gap. If there is, identify the department and regions that should be the focus of management
4. A recent regulation was adopted which requires manufacturing companies to pay employees a minimum of $90,000
  * Does Palmoria meet this requirement?
  * Show the pay distribution of employees grouped by a band of $10,000. For example:
  * How many employees fall into a band of $10,000 – $20,000, $20,000 – $30,000, etc.?
  * Also visualize this by regions.
5. Mr Gamma thought to himself that since you were already working on the employee data, you could help out with allocating the annual bonus pay to employees based on the
performance rating. He handed you another data set that contains rules for making bonus payments and asked you to:
  * Calculate the amount to be paid as a bonus to individual employees.
  * Calculate the total amount to be paid to individual employees (salary inclusive of bonus).
  * Total amount to be paid out per region and company-wide.

### Data Analysis
---
-Descriptive Statistics and Aggregation 
Used the "Table tools" tab to create a simplified Bonus Percentage column based on data from the Palmoria Group Bonus Rules table. Also used DAX Query to create calculated columns such as Salary Band, Bonus %, Bonus Amount and Total Amount.

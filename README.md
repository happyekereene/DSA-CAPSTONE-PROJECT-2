# DSA-CAPSTONE-PROJECT-2

### PALMORIA GROUP HUMAN RESOURCE ANALYSIS

[Project Overview](project-overview)

[Objectives](objectives)

[Data Source](data-source)

[Data Description or Characteristics](data-description-or-characteristics)

[Tools Used](tools-used)

[Data Cleaning and Preparation](data-cleaning-and-preparation)

[Exploratory Data Analysis](exploratory-data-analysis)

[Data Analysis](data-analysis)

[Data Visualization and Interpretation](data-visualization-and-interpretation)

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
- Datasets
Raw Dataset (Palmoria Group emp-data.csv) [view](https://canvas.instructure.com/courses/11955369/files/folder/DSA%20Capstone%20Project%20Files?preview=302720549), (Palmoria Group Bonus Rules.xlsx) [view](https://canvas.instructure.com/courses/11955369/files/folder/DSA%20Capstone%20Project%20Files?preview=302720540).

1. The Palmoria Group emp-data: This contains the employees information about their name, gender, department, location and performance rating.
2. Palmoria Group Bonus Rules contains: This contains the company's bonus allocation criteria for the different departments based on the employees' performance ratings (Very Good, Good, Average, Poor and Very Poor).

### Tools Used
---
- Microsoft PowerBI Desktop [Download Here](https://www.microsoft.com/en-us/download/details.aspx?id=58494)
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
1. Descriptive Statistics and Aggregation 
  * Used the Table tools tab to create a simplified Bonus% table based on data from the Palmoria Group Bonus Rules table.
  * Also used DAX Query to create calculated columns such as Salary Band, Bonus %, Bonus Amount and Total Amount in the main table (The Palmoria Group emp-data).
2.  Queries
  * Calculation of the "Salary Band" column

    Salary Band =
              IF('Palmoria Group emp-data'[Salary]<=30000,"$21K-$30K",
              IF('Palmoria Group emp-data'[Salary]<=40000,"$31K-$40K",
              IF('Palmoria Group emp-data'[Salary]<=50000,"$41K-$50K",
              IF('Palmoria Group emp-data'[Salary]<=60000,"$51K-$60K",
              IF('Palmoria Group emp-data'[Salary]<=70000,"$61K-$70K",
              IF('Palmoria Group emp-data'[Salary]<=80000,"$71K-$80K",
              IF('Palmoria Group emp-data'[Salary]<=90000,"$81K-$90K",
              IF('Palmoria Group emp-data'[Salary]<=100000,"$91K-$100K",
              IF('Palmoria Group emp-data'[Salary]<=110000,"$101K-$110K","$111K-$120K"))))))))) 

  * Calculation of the "Bonus %" column

    Bonus % =
          LOOKUPVALUE('Bonus% Table'[Bonus Percentage],
                      'Bonus Rules'[Department],'Palmoria Group emp-data'[Department],
                      'Bonus% Table'[Rating],'Palmoria Group emp-data'[Rating],0)

3. Calculation of the "Bonus Amount" column

    Bonus Amount =
          'Palmoria Group emp-data'[Salary]*'Palmoria Group emp-data'[Bonus %]

5. Calculation of the "Total Amount" column

    Total Amount =
          'Palmoria Group emp-data'[Salary]+'Palmoria Group emp-data'[Bonus Amount]

### Data Visualization and Interpretation
---
- Excel Dashboard (AMAZON PRODUCT RATING AND REVIEW)

<img width="420" height="336" alt="Palmoria Group Visuals" src="https://github.com/user-attachments/assets/6fabd963-7cd4-4d04-b4af-c4e03faa0236" />

Upon creating the required calculated columns, data-driven insights were created. Building on those insights, we generated an interactive and visually engaging dashboard to effectively communicate our findings. 

The dashboard consists of:

- **Key Performance Indicators (KPIs)**
1. Number of Employees: 874
2. Gender: 3
3. Departments: 12
4. Location: 3
5. Salary >= $90,000: 292
6. Bonus Amount: $959,894.40
7. Total Amount: $31,784,474.40
   
- **Slicer**
1. Gender
2. Departments
3. Locations

- **Key Insights (Charts)**
1. Gender Distribution of Employees
2.	Gender Distribution by Department
3.	Gender Distribution by Region
4.	Distribution of Ratings Based on Gender
5.	Average Salary by Gender
6.	Salary Band by Region
7.	Total Amount Paid Per Region

- **Key Insights in Details
1.	Gender Distribution of Employees
o	Males: 465 (53.15%)
o	Females: 441 (46.62%)
o	Unspecified: 40 (4.23%)
✅ The company has an almost equal gender balance, with a slight male majority.
2.	Gender Distribution by Department
o	Most departments show a fairly balanced gender mix, though some like Product and Engineering have more males.
✅ Diversity initiatives could target departments with low female representation.
3.	Gender Distribution by Region
o	All regions (Kaduna, Abuja, Lagos) have relatively even gender representation, but Kaduna has the highest number of employees.
✅ Recruitment might be more active in Kaduna or it serves as a major operational hub.
4.	Average Salary by Gender
o	Unspecified: $78K
o	Male: $75K
o	Female: $72K
✅ Gender pay gaps are relatively small but still noticeable. Further auditing is recommended.












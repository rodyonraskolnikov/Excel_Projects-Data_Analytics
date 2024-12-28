# Project_1: Salary Dashboard

![1_Salary_Dashboard.png](/0_Resources/Images/1_Salary_Dashboard_Final_Dashboard.gif)

## Introduction

This dashboard serves as a valuable resource for job seekers looking to explore salary trends and ensure they are fairly compensated for their desired roles. By providing clear insights into various positions, salary ranges, and regional differences, the tool empowers users to make informed career decisions. It highlights key data points that are crucial for understanding the current job market.

The information presented in this dashboard is derived from Luke Barousse's Excel course, which focuses on building a strong foundation in data analysis using this versatile tool. The dataset includes detailed information on job titles, compensation levels, locations, and essential skills, making it an excellent example of how Excel can be used to interpret and visualize complex data effectively.

### Dashboard File
My final dashboard is in [Salary_Dashboard.xlsx](Salary_Dashboard.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Data Jobs Dataset

The dataset utilized for this project features real-world information on data science jobs from 2023. This dataset is accessible through [Luke's Excel Course](https://youtu.be/pCJ15nGFgVg?si=SBTaweIOXg8R4InT), which offers a solid foundation in data analysis using Excel. The data provides comprehensive details on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img src="/0_Resources/Images/1_Salary_Dashboard_Chart1.png" width="850" height="550" alt="Salary Dashboard Chart1">

- 🛠️ **Excel Features:** Applied the bar chart feature with salary values formatted for precision and arranged the layout for maximum clarity.
- 🎨 **Design Choice:** Selected a horizontal bar chart to make it easier to compare median salaries visually.
- 📉 **Data Organization:** Job titles were sorted in descending order of salary to enhance readability and focus.
- 💡 **Insights Gained:** Facilitates swift identification of salary patterns, revealing that senior positions and engineering roles typically command higher salaries than analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

![1_Salary_Dashboard_Chart2.png](/0_Resources/Images/1_Salary_Dashboard_Country_Map.gif)

- 🛠️ **Excel Features:** Made use of Excel's map chart feature to visually display median salaries on a global scale.
🎨 **Design Choice:** Implemented a color-coded map to effectively illustrate salary variations across different regions.
📊 **Data Representation:** Displayed the median salary for each country based on the available data.
👁️ **Visual Enhancement:** Enhanced readability to provide an instant overview of geographic salary trends.
💡 **Insights Gained:** Offers a clear understanding of global salary disparities, pinpointing regions with the highest and lowest salaries.

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- 🔍 **Multi-Criteria Filtering:** Filters data based on job title, country, schedule type, and excludes entries with blank salary values.
- 📊 **Array Formula:** Employs the MEDIAN() function combined with a nested IF() statement to process an array of relevant data.
- 🎯 **Tailored Insights:** Delivers precise salary information tailored to specific job titles, locations, and schedule types.
- **🔢 Formula Purpose:** This formula populates the underlying table, calculating the median salary by dynamically considering the specified job title, country, and schedule type.

🍽️ Background Table

![1_Salary_Dashboard_Screenshot1.png](/0_Resources/Images/1_Salary_Dashboard_Screenshot1.png)

📉 Dashboard Implementation

<img src="/0_Resources/Images/1_Salary_Dashboard_Job_Title.png" width="400" height="500" alt="Salary Dashboard Title">

#### ⏰ Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```
- 🔍 **Unique List Generation:** Utilizes the `FILTER()` function in Excel to generate a unique list by excluding entries that contain "and" or commas, as well as omitting any zero values.  
- 🔢 **Formula Purpose:** This formula dynamically creates a table that provides a distinct list of job schedule types, ensuring clean and accurate data representation.  

🍽️ Background Table

![1_Salary_Dashboard_Type.png](/0_Resources/Images/1_Salary_Dashboard_Screenshot2.png)

📉 Dashboard Implementation:

<img src="/0_Resources/Images/1_Salary_Dashboard_Type.png" width="350" height="500" alt="Salary Dashboard Type">

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Applied the filtered list as a data validation rule for the `Job Title`, `Country`, and `Type` fields under the Data tab to ensure:  
  - 🎯 User input is limited to predefined, validated schedule types, maintaining data accuracy.  
  - 🚫 Prevents incorrect or inconsistent entries, reducing errors.  
  - 👥 Improves the overall usability and reliability of the dashboard for end users.  

<img src="/0_Resources/Images/1_Salary_Dashboard_Data_Validation.gif" width="425" height="400" alt="Salary Dashboard Data Validation">

## Conclusion

I developed this dashboard to highlight salary trends across a range of data-related job titles. Drawing from the dataset featured in [Luke Barousse's Excel Course](https://youtu.be/pCJ15nGFgVg?si=SBTaweIOXg8R4InT), it empowers users to make well-informed career decisions. The dashboard also explores how factors like location and job type impact salary outcomes, providing valuable insights for navigating career paths.

# Project 2 Skill/Job Analysis

## Introduction

As a former job seeker, I was often struck by the limited data available on identifying the most desirable jobs and skills in the data science market. Motivated by this gap, I set out to analyze the key skills top employers prioritize and uncover strategies for securing higher compensation.

### Questions to Analyze

To gain insights into the data science job market, I explored the following questions:  

1. **Do additional skills lead to higher pay?**  
2. **What are the salary trends for data-related jobs across different regions?**  
3. **Which skills are most in demand among data professionals?**  
4. **What is the compensation for the top 10 most sought-after skills?**

### Excel Skills Used

The analysis leveraged the following Excel skills:  

- **📊 Pivot Tables**: To organize and summarize complex datasets.  
- **📈 Pivot Charts**: For dynamic visual representation of the data.  
- **🧮 DAX (Data Analysis Expressions)**: To create advanced calculations and measures.  
- **🔍 Power Query**: For efficient data transformation and cleaning.  
- **💪 Power Pivot**: To manage and analyze large datasets seamlessly.  

### Data Jobs Dataset

The dataset for this project features real-world data science job information from 2023 and is accessible through [Luke Barousse's Excel Course](https://youtu.be/pCJ15nGFgVg?si=SBTaweIOXg8R4InT), which offers a comprehensive foundation in data analysis using Excel.  

It provides detailed insights into:  

- **👨‍💼 Job Titles**  
- **💰 Salaries**  
- **📍 Locations**  
- **🛠️ Skills**  

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

- I began by utilizing Power Query to extract the original dataset from `data_salary_all.xlsx` and created two distinct queries:  
  - 🗃️ **First Query:** Included comprehensive information on all data-related jobs.  
  - 🔧 **Second Query:** Focused on listing the skills associated with each unique job ID.
  - 
#### 🔄 Transform

- Next, I refined each query by modifying column types to match the data format, removing irrelevant columns, sanitizing text to remove specific words, and trimming any extra whitespace for a cleaner dataset.
    - 📊 data_jobs_all

        ![2_Project_Analysis_Screenshot1.png](/0_Resources/Images/2_Project_Analysis_Screenshot1.png)

    - 🛠️ data_job_skills

        ![2_Project_Analysis_Screenshot2.png](/0_Resources/Images/2_Project_Analysis_Screenshot2.png)

#### 🔗 Load

- Finally, I imported both transformed queries into the workbook, establishing a solid foundation for the subsequent analysis.
    - 📊 data_jobs_all

        ![2_Project_Analysis_Screenshot3.png](/0_Resources/Images/2_Project_Analysis_Screenshot3.png)

    - 🛠️ data_job_skills

        ![2_Project_Analysis_Screenshot4.png](/0_Resources/Images/2_Project_Analysis_Screenshot4.png)

### 📊 Analysis

#### 💡 Insights

- 📈 A positive correlation exists between the number of skills listed in job postings and the median salary, especially for roles such as Senior Data Engineer and Data Scientist.  
- 💼 Positions requiring fewer skills, such as Business Analyst, generally offer lower salaries, indicating that specialized skill sets are highly valued in the market.  

    ![2_Project_Analysis_Chart1.png](/0_Resources/Images/2_Project_Analysis_Chart1.png)

#### 🤔 So What

- This trend highlights the importance of developing a diverse set of relevant skills, especially for those aspiring to secure higher-paying positions.
- 
## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈Pivot Table

- 🔢 I utilized the Data Model built with Power Pivot to create a PivotTable.  
- 📊 Placed `job_title_short` in the rows area and `salary_year_avg` in the values area for an organized summary.  
- 🧮 Added a new measure to compute the median salary specifically for jobs located in the United States.  
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- I used DAX to calculate the median annual salary, ensuring accurate and dynamic analysis within the Data Model.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights

- 💼 Roles such as Senior Data Engineer and Data Scientist consistently offer higher median salaries both in the US and internationally, reflecting the global demand for advanced data expertise. 
- 💰 A significant salary gap exists between US and Non-US positions, particularly in high-tech roles, likely due to the US's prominence as a hub for the tech industry.  

    ![2_Project_Analysis_Chart2.png](/0_Resources/Images/2_Project_Analysis_Chart2.png)

#### **🤔 So What**

- These salary insights are crucial for career planning and salary negotiations, enabling professionals and organizations to align compensation packages with market benchmarks while accounting for regional differences.
  
## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 I built a data model by combining the `data_jobs_all` and `data_jobs_skills` tables into a unified structure.  
- 🧹 With the data already cleaned using Power Query, Power Pivot automatically established a relationship between the two tables.  

#### 🔗 Data Model

- I established a relationship between the two tables in my data model using the `job_id` column as the key.

    ![2_Project_Analysis_Screenshot5.png](/0_Resources/Images/2_Project_Analysis_Screenshot5.png)

#### 📃 Power Pivot Menu

- The Power Pivot menu was utilized to refine my data model, simplifying the process of creating and managing measures.
- 
    ![2_Project_Analysis_Screenshot6.png](/0_Resources/Images/2_Project_Analysis_Screenshot6.png)

### 📊Analysis

#### 💡Insights

- 💻 SQL and Python stand out as the most sought-after skills in data-related roles, emphasizing their critical role in data processing and analysis.  
- ☁️ The prominence of emerging technologies like AWS and Azure highlights the industry's increasing reliance on cloud services and big data solutions.  

    ![2_Project_Analysis_Chart3.png](/0_Resources/Images/2_Project_Analysis_Chart3.png)

#### 🤔So What

- Identifying prevalent industry skills empowers professionals to remain competitive while also shaping training and educational programs to prioritize the most valuable and impactful technologies.
  
## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to display median salary and skill likelihood (%) from my PivotTable.  
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)  
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)  
- To customize the chart, I added an axis title, removed the lines (skill likelihood), and updated the markers to diamonds.  

### 📊 Analysis

#### 💡Insights

- 💰 Skills such as Python, Oracle, and SQL are linked to higher median salaries, highlighting their essential role in securing high-paying tech positions.  
- 📉 Conversely, skills like PowerPoint and Word are associated with the lowest median salaries and demand, reflecting their limited specialization and relevance in high-salary industries.
  
    ![2_Project_Analysis_Chart4.png](/0_Resources/Images/2_Project_Analysis_Chart4.png)

### 🤔So What

- This chart underscores the value of dedicating time to acquiring high-impact skills such as Python and SQL, as they are clearly linked to higher-paying roles, particularly for individuals aiming to optimize their earnings in the tech sector.
  
## Conclusion

As a passionate data enthusiast and former job seeker, I undertook this Excel-driven project to gain meaningful insights into the data science job market. Drawing from a dataset of real-world job postings, I analyzed job titles, salaries, locations, and essential skills. By utilizing powerful Excel tools such as Power Query, PivotTables, DAX, and charts, I identified significant correlations between possessing multiple skills and earning higher salaries, particularly with expertise in Python, SQL, and cloud technologies.

I hope this project acts as a valuable resource for data professionals, offering a practical roadmap to the skills necessary for securing higher-paying roles and advancing in the industry.

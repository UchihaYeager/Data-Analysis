# Introduction
Dive into the data job market! Focusing on data analyst roles,
this project explores top-paying jobs, in-demand skills and 
where high demand meets high salary in data analytics.

For actual queries, check them here:
[project_sql](/project_sql/)

# Background
Driven by a need to navigate the data analyst job makret efficiently,
the project came from a desire to pinpoint top paid and in-demand
skills, streamlining others work to find optimal jobs.

### Questions I aimed to answer:

1. What are the top-paying data analyst jobs?
2. What skills are required form these jobs?
3. What skills are most in-demand for data analysts?
4. Which skills are associated with higher salaries?
5. What are the most optimal skills to learn?

# Tools used
- **SQL**: The backbones of my analysis, allowing me to query the database 
and unearth critical insights.
- **PostgreSQL**: The chosen database management system, ideal for handling 
the job posting data
- **Visual Studio Code**: My go-to for database management and running 
SQL queries
- **Git & Github**: Essential for version control and sharing my SQL
scripts and analysis, maintaining collaboration and project 
tracking 

# Analysis
Each query for this project aimed at investigating certain aspects of the 
data analyst job market.
Here's how I approached each question:

### 1. Top Paying Data Analyst jobs
To identtify the highest-paying roles, I filtered data analyst positions
by average yearly salary and location. This query highlights the high 
opportunities in the field. 

```sql
SELECT
    job_id,
    job_title,
    job_location,
    job_schedule_type,
    salary_year_avg,
    job_posted_date,
    name AS company_name
FROM
    job_postings_fact
LEFT JOIN company_dim ON job_postings_fact.company_id = company_dim.company_id
WHERE
    job_title_short = 'Data Analyst' AND 
    job_location LIKE '% Africa' AND
    salary_year_avg IS NOT NULL

ORDER BY 
    salary_year_avg DESC

LIMIT 10;
```

Here's the breakdown of the top data analyst jobs for the year 2023 in South Africa:
- **Wide Salary Range:** Top 10 paying data analyst roles span from $100,500 to 
$165,000, indicating significant salary potential in the field.
- **Diverse Employers:** Companies like Takealot, Deloitte and Standard are among 
those offering high salaries, showing a wide interest across different industries.
- **Job Title Variett:** There's a high diversity in job titles, reflecting varied 
roles and specializations within data analytics.

# What I learned
- **Complex Query Crafting:** Mastered the art of Advanced SQL, merging tables and 
wielding WITH clauses for high level temp tables.
- **Data Aggregation:** Got cozy with GROUP BU and turned aggregate functions like
COUNT() and AVG() into data-summarizing tools.
- **Analytical knowledge:** Leveled up my real-world puzzle-solving skills, turning
questions into actionable, insightful SQL queries.

# Conclusions

### Insights

1. **Skills for top-paying jobs:** High paying data analyst jobs require advanced
proficiency in SQL, suggesting it's a critical skill for earning a top salary.
2. **Most in-demand skills:** SQL is also the most demanded skill in the data 
analyst job market, therefore making it essential for job seekers.
3. **Optimal skills for Job Market Value:** SQL leads in demand and offers for a 
high average salary placing it at the top of the most optimal skills for data 
analytics to learn to maximize their market value.

### Closing Thoughts

This project enhanced my SQL skills and provided valuable insights into the data
anakyst job market. The findings from the analysis serve as a guide to prioritizing
skill development and job search efforts. Aspiring data analysts can better position
themselves in a competitive job market by focusing on high-demand, high-salary 
skills. This exploration highlights the importance of continuous learning and 
adaptaion to emerging trends in the field of data analytics.

# HR-analytics
**HR analytics, also known as people analytics, is a data-driven approach to managing human resources. It involves gathering and analyzing data related to employees, such as recruitment, performance, engagement, and retention, to derive insights and make informed decisions.**

## CASE STUDY OVERVIEW

### Organization Description:
Let's consider a medium-sized technology company called *"TechSolutions Inc."* The company specializes in software development and has a diverse workforce across different departments, including engineering, marketing, sales, and customer support.

## Objectives:
### The main objectives of this case study are as follows:
- Understand the factors influencing employee attrition and job satisfaction.
- Identify key predictors of employee performance.
- Develop strategies to improve employee engagement and retention.
- DATA COLLECTION AND ANALYSIS

## Data Sources:
### To conduct HR analytics, the following data sources are utilized:

- HRIS (Human Resource Information System): Employee demographic information, employment history, and compensation details.
- Performance Management System: Employee performance ratings, goals, and achievements.
- Employee Surveys: Feedback on job satisfaction, work-life balance, and engagement.
- Exit Interviews: Reasons for employee departures and feedback on their experiences.
**The dataset containing employee data was obtained from Kaggle**

## Processing & Analysis 
**I will use SQL to carry out the analysis for each part**
### PART ONE:

Attrition Analysis: Analyze historical data to understand factors contributing to employee attrition, such as department, job level, salary, tenure, performance ratings, and employee demographics.


```
SELECT Department, (COUNT(CASE WHEN Attrition = true THEN 1 END)/COUNT(*))*100 AS AttritionRate
FROM `sql-practice-392607.HR_Data_Analytics.Employee-attrition`
GROUP BY Department


SELECT JobLevel, (COUNT(CASE WHEN Attrition = true THEN 1 END)/COUNT(*))*100 AS AttritionRate
FROM `sql-practice-392607.HR_Data_Analytics.Employee-attrition`
GROUP BY JobLevel


SELECT (COUNT(CASE WHEN Attrition = true THEN 1 END)/COUNT(*))*100 AS AttritionRate, 
  CASE 
    WHEN HourlyRate BETWEEN 0 and 40 then "0-40"
    WHEN HourlyRate BETWEEN 41 and 50 then "41-50"
    WHEN HourlyRate BETWEEN 51 and 60 then "51-60"
    WHEN HourlyRate BETWEEN 61 and 70 then "61-70"
    WHEN HourlyRate BETWEEN 71 and 80 then "71-80"
    WHEN HourlyRate BETWEEN 81 and 90 then "81-90"
    ELSE "91+"
  END AS RateByHour
FROM `sql-practice-392607.HR_Data_Analytics.Employee-attrition`
GROUP BY 
  CASE 
    WHEN HourlyRate BETWEEN 0 and 40 then "0-40"
    WHEN HourlyRate BETWEEN 41 and 50 then "41-50"
    WHEN HourlyRate BETWEEN 51 and 60 then "51-60"
    WHEN HourlyRate BETWEEN 61 and 70 then "61-70"
    WHEN HourlyRate BETWEEN 71 and 80 then "71-80"
    WHEN HourlyRate BETWEEN 81 and 90 then "81-90"
    ELSE "91+"
  END


SELECT YearsAtCompany, (COUNT(CASE WHEN Attrition = true THEN 1 END)/COUNT(*))*100 AS AttritionRate
FROM `sql-practice-392607.HR_Data_Analytics.Employee-attrition`
GROUP BY YearsAtCompany


SELECT Gender, (COUNT(CASE WHEN Attrition = true THEN 1 END)/COUNT(*))*100 AS AttritionRate
FROM `sql-practice-392607.HR_Data_Analytics.Employee-attrition`
GROUP BY Gender


SELECT MaritalStatus, (COUNT(CASE WHEN Attrition = true THEN 1 END)/COUNT(*))*100 AS AttritionRate
FROM `sql-practice-392607.HR_Data_Analytics.Employee-attrition`
GROUP BY MaritalStatus


SELECT RelationshipSatisfaction, (COUNT(CASE WHEN Attrition = true THEN 1 END)/COUNT(*))*100 AS AttritionRate
FROM `sql-practice-392607.HR_Data_Analytics.Employee-attrition`
GROUP BY RelationshipSatisfaction


SELECT (COUNT(CASE WHEN Attrition = true THEN 1 END)/COUNT(*))*100 AS AttritionRate,
    CASE 
      WHEN DistanceFromHome BETWEEN 0 and 10 then "0-5"
      WHEN DistanceFromHome BETWEEN 11 and 15 then "11-15"
      WHEN DistanceFromHome BETWEEN 16 and 20 then "16-20"
      ELSE "21+"
    END AS Distance
FROM `sql-practice-392607.HR_Data_Analytics.Employee-attrition`
GROUP BY 
  CASE 
    WHEN DistanceFromHome BETWEEN 0 and 10 then "0-5"
    WHEN DistanceFromHome BETWEEN 11 and 15 then "11-15"
    WHEN DistanceFromHome BETWEEN 16 and 20 then "16-20"
    ELSE "21+"
  END 
```

________________
TBC

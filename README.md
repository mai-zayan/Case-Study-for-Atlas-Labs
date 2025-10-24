# 🧠 Atlas Labs - HR Analytics Dashboard

A comprehensive **Power BI Dashboard** built to analyze workforce data for **Atlas Labs** — focusing on employee demographics, performance trends, and attrition insights.  
This interactive report helps HR and management teams make **data-driven decisions** to enhance retention, satisfaction, and productivity.

---

## 📘 Project Summary

This Power BI project visualizes the entire employee lifecycle — from **hiring** and **performance** to **attrition**.  
The dashboard is divided into **four main sections**:

1. **Overview**
2. **Demographics**
3. **Performance Tracker**
4. **Attrition Analysis**

📂 File: `Case Study - Atlas Labs.pbix`

---

## 📊 Dashboard Sections

### 🟣 1. Overview
- Total Employees: **1470**
- Active Employees: **1233**
- Inactive Employees: **237**
- Attrition Rate: **16.1%**
- Hiring Trends (2012–2022)
- Active Employees by Department & Job Role

![overview](https://github.com/user-attachments/assets/773b419f-66af-4382-8e94-be94f5538ede)


---

### 🟪 2. Demographics
- Age Distribution & Gender Ratio  
- Youngest Employee: **18 years**  
- Oldest Employee: **51 years**  
- Marital Status Composition  
- Ethnicity vs. Average Salary

![demographics](https://github.com/user-attachments/assets/dca18228-68be-406e-bdc1-38aa63367491)


---

### 🟫 3. Performance Tracker
Track satisfaction and engagement metrics over time:
- Environment Satisfaction  
- Job Satisfaction  
- Self-Rating  
- Work-Life Balance  
- Relationship Satisfaction  
- Manager Rating  

![performance tracker](https://github.com/user-attachments/assets/a77f9730-1b6e-47a6-9a4a-c06390763e42)
 


---

### 🟦 4. Attrition Analysis
Gain insights into employee turnover patterns:
- Attrition Rate by Department & Job Role  
- Attrition by Travel Frequency  
- Attrition by Overtime  
- Attrition by Hire Date  
- Attrition by Tenure  

![attrition](https://github.com/user-attachments/assets/de70f562-db1b-4c8e-8aa6-a82fb3f26bbe)


---

## 📈 Key Insights

The **Atlas Labs HR Dashboard** provides actionable insights into workforce dynamics:

| Insight | Observation |
|----------|--------------|
| 👥 **Department Size** | The **Technology Department** has the largest employee base. |
| 📉 **Attrition Hotspots** | The **Sales** and **HR** departments show the **highest attrition rates**. |
| 🧓 **Age Distribution** | Majority of employees fall between **20–29 years** — indicating a young workforce. |
| ⏰ **Overtime Impact** | Employees doing **frequent overtime** show a **higher chance of leaving**. |
| ✈️ **Travel Frequency** | Frequent business travel correlates with increased attrition. |
| 📅 **Tenure Trend** | Employees who stayed beyond **5 years** have significantly lower attrition. |
| 😐 **Satisfaction Levels** | **Job** and **Manager Satisfaction** have been decreasing since **2019**. |
| 💸 **Salary Gap** | Notable variation in **average salary** across different ethnicities and roles. |

These insights enable the HR team to **predict employee turnover** and **improve engagement strategies**.

---

## ⚙️ Tools & Technologies

| Tool | Purpose |
|------|----------|
| **Power BI Desktop** | Data visualization & report design |
| **Power Query** | Data cleaning & transformation |
| **DAX (Data Analysis Expressions)** | KPI calculations |
| **Excel / CSV** | Data source |
| **GitHub** | Version control & documentation |

---

## 🧮 DAX Measures (Key Calculations)

### 📌 Core KPIs
```DAX
Total Employee = COUNTROWS(Employee)

Active Employee = CALCULATE(
    COUNTROWS(Employee),
    FILTER(Employee, Employee[Status] = "Active")
)

Inactive Employee = [Total Employee] - [Active Employee]

Attrition Count = CALCULATE(
    COUNTROWS(Employee),
    FILTER(Employee, Employee[Attrition] = "Yes")
)

Attrition Rate = DIVIDE([Attrition Count], [Total Employee], 0)
Active Employee by Department =
CALCULATE(
    [Active Employee],
    ALLEXCEPT(Employee, Employee[Department])
)

Attrition by Department =
CALCULATE(
    [Attrition Count],
    ALLEXCEPT(Employee, Employee[Department])
)
Average Salary = AVERAGE(Employee[Salary])

Avg Salary by Ethnicity =
CALCULATE(
    AVERAGE(Employee[Salary]),
    ALLEXCEPT(Employee, Employee[Ethnicity])
)

Performance Score =
AVERAGEX(
    VALUES(Employee[Year]),
    (Employee[JobSatisfaction] +
     Employee[ManagerRating] +
     Employee[WorkLifeBalance] +
     Employee[RelationshipSatisfaction]) / 4
)
🧠 Data Model Structure

| Table            | Description               | Key Columns                                          |
| ---------------- | ------------------------- | ---------------------------------------------------- |
| **Employee**     | Core HR dataset           | EmployeeID, Gender, Department, JobRole              |
| **Performance**  | Individual yearly ratings | EmployeeID, Year, SelfRating, ManagerRating          |
| **Satisfaction** | Survey data               | EmployeeID, EnvironmentSatisfaction, JobSatisfaction |
| **Salary**       | Compensation info         | EmployeeID, Salary, Ethnicity                        |
| **Attrition**    | Employment exit data      | EmployeeID, Attrition, HireDate, TerminationDate     |

🚀 How to Use

Clone this repository

git clone https://github.com/mai-zayan/Case-Study-for-Atlas-Labs


Open in Power BI Desktop

Case Study - Atlas Labs.pbix


Refresh Data (if needed)

Go to Home → Transform Data → Data Source Settings

Update dataset path if necessary

Click Refresh All

Explore Dashboards

Overview

Demographics

Performance Tracker

Attrition

📁 Repository Structure
├── Case Study - Atlas Labs.pbix       # Power BI dashboard file
├── overview.jpg                       # Overview page screenshot
└── README.md                          # Project documentation

👨‍💻 Author

Name: Mai Zayan


🪪 License

This project is licensed under the MIT License
.

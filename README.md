# Employee Attendance & Watch Monitoring Dashboard

A Power BI dashboard developed to analyze employee attendance, access-control activity, and watch assignment status.

The project combines attendance records from two systems and provides an interactive dashboard for monitoring employee presence, attendance discrepancies, and watch usage.

> **Note:** This GitHub repository contains synthetic/anonymized data created for demonstration purposes. No original company data or confidential employee information is included.

---

## 📊 Dashboard Overview

The dashboard provides an interactive view of employee attendance across multiple dates, plants, departments, sections, and watch-status categories.

### Key KPIs

- Total Records
- Present in Both Systems
- Fortuna Only
- Access Only
- Absent
- Present & Wearing Watch
- Present & Not Wearing Watch

### Dashboard Visualizations

- Attendance status distribution
- Daily attendance trends
- Plant-wise employee analysis
- Watch assignment analysis
- Attendance comparison between systems
- Employee-level attendance table
- KPI cards
- Interactive slicers and filters

---

## 🛠️ Technologies Used

- **Power BI**
- **Power Query**
- **DAX**
- **Microsoft Excel**

---

## 🔄 Data Processing Workflow

The data processing pipeline was implemented using Power Query.

```text
Synthetic Employee Data
        │
        ▼
   Power Query
        │
        ├── Data Cleaning
        ├── Data Type Transformation
        ├── Duplicate Removal
        ├── Data Merging
        ├── Attendance Classification
        └── Watch Status Classification
        │
        ▼
 EmployeeUniverse Dataset
        │
        ▼
      DAX Measures
        │
        ▼
   Power BI Dashboard
📋 Attendance Classification

Employees are classified into four attendance categories:

Status	Description
Present in Both	Employee is present in both attendance systems
Fortuna Only	Employee appears only in the Fortuna attendance system
Access Only	Employee appears only in the Access attendance system
Absent	Employee has no attendance record for the selected date
⌚ Watch Status Analysis

The dashboard also analyzes whether employees were assigned a watch.

Status	Description
Watch Assigned	Employee has a watch assigned
No Watch Assigned	Employee does not have a watch assigned

The dashboard combines attendance and watch information to identify:

Present employees with an assigned watch
Present employees without an assigned watch
📈 DAX Measures

DAX measures were created for the dashboard KPIs.

Present & Wearing Watch
Present_Wearing_Watch =
FORMAT(
    CALCULATE(
        COUNTROWS(EmployeeUniverse_new),
        EmployeeUniverse_new[Watch Status] = "Watch Assigned",
        EmployeeUniverse_new[AttendanceStatus] <> "Absent"
    ),
    "#,##0"
)
Present & Not Wearing Watch
Present_Not_Wearing_Watch =
FORMAT(
    CALCULATE(
        COUNTROWS(EmployeeUniverse_new),
        EmployeeUniverse_new[Watch Status] = "No Watch Assigned",
        EmployeeUniverse_new[AttendanceStatus] <> "Absent"
    ),
    "#,##0"
)

These measures are used to display exact KPI values on the dashboard.

🎛️ Interactive Filters

The dashboard includes slicers for:

Date
Plant
Department
Section
Watch Status

These filters allow users to analyze attendance for specific groups of employees.

📊 Dashboard Insights

The dashboard enables users to analyze:

Overall employee attendance
Attendance overlap between two systems
Employees appearing in only one attendance system
Employee absence patterns
Watch assignment coverage
Employees present without an assigned watch
Daily attendance trends
Plant-wise attendance distribution
Department and section-level attendance
📁 Repository Structure
Employee-Attendance-PowerBI-Dashboard/
│
├── Employee_Attendance_Dashboard.pbix
│
├── Synthetic_EmployeeUniverse.xlsx
│
├── dashboard.png
│
└── README.md
Files

Employee_Attendance_Dashboard.pbix
Power BI report containing the data model, Power Query transformations, DAX measures, and dashboard visualizations.

Synthetic_EmployeeUniverse.xlsx
Synthetic employee dataset used to demonstrate the dashboard without exposing proprietary company data.

dashboard.png
Preview of the completed Power BI dashboard.

README.md
Project documentation and explanation of the dashboard.

🔐 Data Privacy

This repository does not contain original company attendance files or confidential employee records.

The dataset included in this repository has been created/anonymized specifically for portfolio demonstration.

💡 Key Learning Outcomes

Through this project, I worked with:

Power Query data transformation
Data cleaning and preprocessing
Merging datasets using common employee/date keys
Handling duplicate records
Attendance classification
DAX calculated measures
KPI development
Interactive Power BI dashboards
Data visualization
Filtering and drill-down analysis
Building a Power BI data model
Creating calculated KPIs
Combining multiple data sources
Designing business-oriented dashboards
🚀 How to Use
Download the .pbix file from this repository.
Open it using Microsoft Power BI Desktop.
If required, update the Power Query source path to the included synthetic Excel file.
Refresh the dataset.
Use the dashboard filters to explore the data.
📌 Project Purpose

The purpose of this project is to demonstrate how employee attendance data from multiple systems can be transformed, classified, and visualized using Power BI to provide actionable insights through an interactive dashboard.

The project focuses on practical data analytics workflows including data preprocessing, data integration, KPI creation, and interactive visualization.

👨‍💻 Author

Jinendra Sethia

Information Technology
Manipal Institute of Technology, Bengaluru


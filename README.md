
# 🏥 Hospital Weekend Report Automation Project

## 📋 Overview

The **Hospital Weekend Report Automation System** is a complete solution designed to streamline the collection, aggregation, and visualization of hospital statistics over weekends. It eliminates manual Excel tracking, increases data accuracy, and enables real-time monitoring via **Power BI**.

---

## 📊 Project Goals

- Collect daily hospital statistics via a **Google Form**
- Automate form data transfer to a **Google Sheet**
- Use **Power Automate** to load Google Sheet data into a **Power BI Dataset**
- Design comprehensive dashboards and KPIs for decision-making
- Enable live, filterable reports across wards, days, and patient metrics

---

## 🧱 System Architecture

```
[User] --> [Google Form] --> [Google Sheet] --> [Power Automate] --> [Power BI Dataset] --> [Power BI Dashboard]
```

### Components:
- **Google Forms**: Data input
- **Google Sheets**: Response storage
- **Power Automate**: Integration bridge to Power BI
- **Power BI**: Visualization and analysis

---

## 🛠 Technologies Used

| Component      | Technology             |
|----------------|------------------------|
| Data Entry     | Google Forms           |
| Data Storage   | Google Sheets          |
| Data Transfer  | Power Automate         |
| Reporting      | Power BI Service + Desktop |
| Auth & Access  | Microsoft 365 & Google Workspace |

---

## 📥 Data Collection: Google Forms

### Form 1: Well People Summary
- **Fields**:
  - Department (choice)
  - Date (date picker)
  - Day (choice)
  - Total Values (number)

Departments include:
- Obs & Gynae
- Paediatrics
- Specialized Surgery
- General Surgery
- Orthopaedics
- Medicine
- etc.

---

### Form 2: In-Patients Statistics
- **Fields**:
  - Day (choice)
  - Date (date picker)
  - Ward (choice list: GFA, GFB, 1A, 1B-HAEMATO, etc.)
  - No. of Admissions (number)
  - No. of Patients (number)

Responses are stored automatically in **linked Google Sheets**.

---

## 🔁 Automation: Power Automate

### Objective:
Move Google Sheets data to Power BI dataset automatically every few minutes.

### Flow Design:
1. **Trigger**: Recurring schedule (e.g., every 15 minutes)
2. **Action 1**: Connect to Google Sheets (Google connector)
3. **Action 2**: Read rows from responses sheet
4. **Action 3**: Format records (apply transformations if needed)
5. **Action 4**: Push records to Power BI Streaming Dataset

---

## 📊 Power BI Dashboards

### Report Pages

#### 📘 Page 1: Well People Summary
- **Visuals**:
  - Total Department Values by Day (Stacked Column)
  - Line Chart: Department Trends Over the Week
  - Pie Chart: Share of Values by Department
  - KPI: Max Day Value
  - KPI: Department with Highest Activity
  - KPI: Total Entries

#### 📗 Page 2: In-Patients Statistics
- **Visuals**:
  - Line Chart: Admissions & Patients Over Time
  - Bar Chart: Top 5 Wards by Admissions
  - Clustered Column: Patients vs Admissions per Ward
  - KPI: Total Admissions This Week
  - KPI: Total Patients This Week
  - KPI: Average Admissions per Day
  - Heatmap Matrix by Day & Ward

### Filters
- Date Picker
- Ward Slicer
- Department Filter
- Day of the Week Filter

---

## 📈 KPIs

1. **Total Admissions (Weekly)**
2. **Total Patients (Weekly)**
3. **Top Performing Ward**
4. **Busiest Day of the Week**

---

## 📂 Folder Structure

```
/ProjectRoot
│
├── GoogleForms/
│   ├── well_people_form_link.txt
│   └── inpatients_form_link.txt
│
├── GoogleSheets/
│   ├── well_people_responses.xlsx
│   └── inpatients_statistics.xlsx
│
├── PowerAutomateFlows/
│   ├── flow_wellpeople_to_powerbi.json
│   └── flow_inpatients_to_powerbi.json
│
├── PowerBI/
│   ├── HospitalReport.pbix
│   └── screenshots/
│       ├── summary_page.png
│       └── patients_page.png
│
└── README.md
```

---

## 🔐 Access Control

- **Forms**: Restricted to authorized hospital staff (via Google account)
- **Google Sheets**: Shared with automation service account and report managers
- **Power BI**: Shared via Microsoft 365 workspace, with view/edit restrictions

---

## 🔧 Setup Instructions

1. **Create Google Forms** based on the fields listed
2. **Connect each Form to its own Google Sheet**
3. In **Power Automate**:
   - Create a flow that reads Google Sheet data
   - Connect the output to a Power BI streaming dataset
4. In **Power BI Desktop**:
   - Connect to dataset
   - Build reports and publish to Power BI Service
5. Schedule regular refresh or live updates via Power Automate
6. Share dashboard with hospital management team

---

## 💡 Best Practices

- Always validate form logic (required fields, choices)
- Maintain consistent column names in Google Sheets
- Periodically back up form responses
- Use naming conventions in flows and dashboards
- Protect sensitive sheets and dashboards using permissions

---

## ✅ Status

| Feature                  | Status     |
|--------------------------|------------|
| Google Forms Setup       | ✅ Complete |
| Google Sheets Integration| ✅ Complete |
| Power Automate Flows     | ✅ Running  |
| Power BI Dashboards      | ✅ Published|
| Real-time Sync           | ✅ Enabled  |

---

## 📧 Contact & Support

If you have any issues or feedback, please contact the **Hospital Data Team**:

- Email: `data.team@hospital.org`
- Team Lead: Jane Doe
- Backup Contact: John Smith

---

## 📌 Future Enhancements

- Add mobile Power BI access via QR code
- Send automated weekly summary emails to executives
- Integrate shift/doctor data with patient volumes
- Historical data trend analysis

---

> _Built with ❤️ for better healthcare decisions_

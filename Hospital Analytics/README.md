# 🏥 Hospital Management & Patient Analytics Dashboard | Power BI

An interactive **Hospital Management Analytics Dashboard** built using **Power BI** to monitor hospital operations, patient appointments, doctor performance, treatment analysis, and financial insights. This project demonstrates data modeling, DAX, data visualization, and business intelligence techniques to support data-driven decision-making.

---

## 📌 Project Overview

Healthcare organizations generate large volumes of operational and financial data. This dashboard transforms raw hospital data into actionable insights by analyzing patient demographics, appointment trends, doctor performance, treatments, and billing information.

The dashboard enables hospital administrators to monitor key performance indicators (KPIs), optimize resource allocation, improve patient care, and track revenue performance through interactive visualizations.

---

## 🎯 Business Problem

Hospital management requires a centralized reporting solution to answer important business questions such as:

- Which doctors handle the highest number of appointments?
- What is the overall appointment completion rate?
- Which treatments generate the highest revenue?
- How much revenue is pending collection?
- Which payment methods are most frequently used?
- What are the monthly appointment and revenue trends?
- Which patient demographics require more attention?

This dashboard provides a comprehensive solution by converting operational data into meaningful business insights.

---

## 📊 Dashboard Pages

### 📄 Page 1 – Executive Overview

#### KPI Cards
- 👥 Total Patients
- 👨‍⚕️ Total Doctors
- 📅 Total Appointments
- 💰 Total Revenue
- ✅ Completed Appointments
- 💳 Pending Revenue

#### Visualizations
- Revenue by Payment Status
- Appointment Status Distribution
- Monthly Revenue Trend
- Top Doctors by Appointments

---

### 📄 Page 2 – Patient & Treatment Analytics

#### Visualizations
- Patient Gender Distribution
- Patients by Insurance Provider
- Most Performed Treatments
- Revenue by Treatment
- Monthly Appointment Trend
- Doctor Performance Matrix
- Revenue Collection Gauge
- Average Treatment Cost

---

## 📂 Dataset

The project consists of five related datasets:

| Dataset | Description |
|----------|-------------|
| Patients | Patient demographic information |
| Doctors | Doctor details and specialization |
| Appointments | Appointment records and status |
| Treatments | Treatment information and cost |
| Billing | Billing amount, payment method, and payment status |

---

## ⭐ Data Model

The project follows a **Star Schema** data model.

```

Dim Patients
│
├──────────────┐
│              │
▼              ▼
Fact Appointments ◄──────── Dim Doctors
│
▼
Fact Treatments
│
▼
Fact Billing

```

### Relationships

| From | To | Relationship |
|------|----|--------------|
| Patients → Appointments | patient_id | One-to-Many |
| Doctors → Appointments | doctor_id | One-to-Many |
| Appointments → Treatments | appointment_id | One-to-Many |
| Treatments → Billing | treatment_id | One-to-One / One-to-Many |

---

## 📈 Key Performance Indicators (KPIs)

- Total Patients
- Total Doctors
- Total Appointments
- Completed Appointments
- Cancelled Appointments
- No-show Appointments
- Total Revenue
- Paid Revenue
- Pending Revenue
- Failed Payments
- Average Treatment Cost

---

## 📊 Power BI Features Used

- Data Cleaning (Power Query)
- Star Schema Data Modeling
- DAX Measures
- Calculated Columns
- Interactive Slicers
- Static RLS
- Tooltips
- KPI Cards
- Line Charts
- Bar Charts
- Donut Charts
- Gauge Charts
- Matrix Tables
- Conditional Formatting

---

## 🧮 Sample DAX Measures

```DAX
Total Revenue =
SUM(Billing[Amount])

Total Patients =
DISTINCTCOUNT(Patients[Patient_ID])

Completed Appointments =
CALCULATE(
COUNT(Appointments[Appointment_ID]),
Appointments[Status]="Completed"
)

Pending Revenue =
CALCULATE(
SUM(Billing[Amount]),
Billing[Payment_Status]="Pending"
)
```

---

## 📌 Business Insights

- Identified appointment completion and cancellation trends.
- Analyzed doctor workload across departments.
- Compared treatment popularity and generated revenue.
- Monitored billing performance and pending payments.
- Evaluated patient demographics and insurance distribution.
- Tracked monthly appointment and revenue trends.

---

## 🛠️ Tools & Technologies

- Microsoft Power BI
- Power Query
- DAX
- Data Modeling
- Microsoft Excel
- Data Visualization
- Business Intelligence

---

## 🚀 Skills Demonstrated

- Data Cleaning
- Data Transformation
- Data Modeling
- Star Schema Design
- DAX Calculations
- Dashboard Design
- KPI Development
- Business Analytics
- Healthcare Analytics
- Data Storytelling

---



---

## 📁 Project Structure

```

Hospital-Management-Analytics/
│
├── Hospital Dashboard.pbix
├── Dataset/
│ ├── appointments.csv
│ ├── patients.csv
│ ├── doctors.csv
│ ├── treatments.csv
│ └── billing.csv
├── Images/
│ ├── Dashboard1.png
│ └── Dashboard2.png
└── README.md

```

---

## 💡 Future Enhancements

- Predict patient appointment no-shows using Machine Learning.
- Department-wise performance dashboard.
- Forecast future hospital revenue.
- Real-time dashboard using SQL Server.
- Role-Level Security (RLS).
- Power BI Service deployment with scheduled refresh.

---

## 👨‍💻 Author

**Hari Prasath H**
---

### ⭐ If you found this project helpful, don't forget to star this repository!

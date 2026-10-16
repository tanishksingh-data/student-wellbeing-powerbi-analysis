# Student Social Media & Well-being Analysis | Power BI Project

An interactive, multi-page Power BI dashboard designed to analyze how student social media consumption impacts sleep architecture, academic performance, mental health, and interpersonal relationships.

---

## 📌 Project Overview
Educational institutions and counselors require data-driven clarity on the side effects of digital engagement. This project ingests behavioral and demographic data to evaluate screen addiction thresholds, lifestyle trade-offs, and scholastic risks across diverse student segments.

### Target Stakeholders
* **Academic Advisors:** Identify high-risk usage patterns correlating with academic decline.
* **Mental Health Counselors:** Track the correlation between screen addiction, sleep deprivation, and mental health ratings.
* **Institutional Researchers:** Segment findings by country, gender, and academic cohort.
* **One-on-One Counselors:** Access diagnostic profiles for individual student interventions via drill-through.

---

## 🏗️ Data Architecture & Modeling

### 1. Source Data
* **`Student Details`:** Contains demographic attributes (`Age`, `Gender`, `Country`, `Academic_Level`, `Relationship_Status`) and well-being metrics (`Sleep_Hours_Per_Night`, `Mental_Health_Score`, `Conflicts_Over_Social_Media`, `Addicted_Score`)[cite: 10, 11].
* **`Platform Details`:** Tracks behavioral metrics (`Avg_Daily_Usage_Hours`, `Most_Used_Platform`, `Affects_Academic_Performance`)[cite: 10, 12].

### 2. Schema Design
* **Primary Relationship:** 1:1 bi-directional/cross-filter relationship between `Student Details[Student_ID]` and `Platform Details[Student_ID]`.
* **Calendar Simulation:** Standalone `DateTable` generated via DAX for time-intelligence extensibility:
  ```dax
  DateTable = CALENDAR(DATE(2023, 1, 1), DATE(2023, 12, 31))

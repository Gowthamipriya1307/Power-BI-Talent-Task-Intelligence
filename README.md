
# 🧠 Talent & Task Intelligence Dashboard (Power BI)


🎥 [Watch the Dashboard Demo (2-min walkthrough)](https://drive.google.com/file/d/1iS848qV88tKRu5bnePINomX3CJxkk1pG/view)


This end-to-end Power BI solution offers strategic insights into workforce attrition risk and task performance across enabling functions. It combines advanced DAX, data modeling, Python-driven synthetic data generation, and Row-Level Security (RLS) to demonstrate enterprise-grade dashboarding and governance capabilities — tailored to roles like Talent Analytics at Accenture.

---

## 📌 Project Objective

To deliver a role-based, insight-driven dashboard that supports:

- SLA compliance and task efficiency tracking  
- Escalation risk and resolution time analysis  
- Workforce attrition pattern discovery  
- Secure, department-specific data access using Row-Level Security (RLS)  

---

## 📊 Key Features

### 🔹 Page 1: Executive Overview
- **KPIs:** SLA Compliance %, Escalation Rate %, Avg Resolution Time, Breach Cost  
- **Visuals:** Monthly SLA Trend, Escalation Analysis, Task Type Performance  
- **Goal:** High-level operational insights for leadership  

### 🔹 Page 2: Task Analysis Drilldown
- **Drillthrough-enabled bar charts** by department & task type  
- **Cost of SLA Breaches by Task Type** (using simulated cost logic)  
- **Overdue Task Monitoring** with dynamic filtering  
- **Bookmark buttons** to toggle detailed views  
- **Goal:** Department managers & analysts track task and SLA efficiency  

### 🔹 Page 3: Workforce Insights
- **Attrition analysis** by age, income, business travel, overtime, tenure  
- **Box plots & heatmaps** (including Python visuals)  
- **At-Risk Employee flags** based on job satisfaction & workload  
- **Key Influencer chart** to identify top drivers of attrition  
- **Goal:** HR teams identify early signs of attrition and burnout  

---

## 🧩 Data Sources

| Table      | Source | Notes |
|------------|--------|-------|
| `EmployeeData` | IBM HR Analytics Dataset (open dataset) | Base employee profiles, satisfaction, job role, income, etc. |
| `TaskLog`      | Simulated using Python | Contains task-level data with SLA hours, actual resolution time, escalation status, etc. |

🛈 _The task data is synthetically generated to mimic realistic operational workflows and support advanced modeling in the absence of real SLA records._

---

## 🔐 Row-Level Security (RLS)

Role-based access is implemented to ensure department-specific visibility.

- **User Table:** Maps simulated emails to departments  
- **DAX Logic:**
  ```DAX
  [Department] = 
  LOOKUPVALUE(
    UserTable[Department],
    UserTable[UserEmail],
    USERPRINCIPALNAME()
  )
  ```
- Tested using **Modeling → View as Role** in Power BI Desktop  
- Optional: Demonstrated in screen recording walkthrough

---

## ⚙️ Technologies & Skills Demonstrated

- **Power BI:** Data modeling, DAX, relationships, bookmarks, drillthrough, tooltips  
- **Python:** Used to generate TaskLog table and create custom visuals  
- **PostgreSQL:** Initial testing for simulated SQL data connection  
- **Power Query:** Column cleanup, merging, transformations  
- **Row-Level Security (RLS):** Governance and role-based access control  

---

## 🧪 How to Use

1. Open the `.pbix` file in Power BI Desktop  
2. Use **View as Role** under Modeling to test RLS per department  
3. Use slicers or buttons to explore task performance or attrition factors  
4. Optionally view the **screen recording** to experience the full interactivity

---

## 📹 Walkthrough

A short [screen recording](https://drive.google.com/file/d/1iS848qV88tKRu5bnePINomX3CJxkk1pG/view) demonstrates key dashboard features, tooltips, buttons, drillthroughs, and RLS simulation.


---

## 📁 File List

- `Talent & Task Intelligence Dashboard.pbix` → Power BI dashboard file  
- `README.md` → This documentation  
- `screenshots/` → Optional image previews per page  
- `screen_recording.mp4` → (optional) walkthrough video  

---

## ✅ Key Takeaways

- Combines real HR data with simulated operational task records  
- Demonstrates complete Power BI lifecycle (data, modeling, UX, security)  
- Aligns with enterprise analytics roles like Talent Intelligence or People Analytics  
- Implements storytelling through theme-consistent, insight-driven visuals  

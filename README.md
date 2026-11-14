# **HR Analytics: Retention, Performance & Attendance | Power BI**

**Author:** Nhu Quynh

**Tools:** SQL / Power BI

[View Interactive Dashboard HERE!](https://app.powerbi.com/view?r=eyJrIjoiYzNjY2FhMDktNmU2Yy00MmE3LTk0NWYtZDRhZjI4Yjk3MTFmIiwidCI6ImVkOGYxNjczLTM4OTAtNGRiNC1hM2YwLTk3YWQ5NDI3Yzc0ZiIsImMiOjEwfQ%3D%3D&pageName=b60b3c152270a064275d)
---
## Table of Content
1. Background and Overview
2. Dataset Description & Data Structure
3. Design Thinking Process
4. Key insight and visualization
5. Final conclusion and recommendation

---
## 1. Background and Overview
**What is this project about**

This project analyzes workforce data across 1,500 employees to support better HR decisions. The Power BI dashboard focuses on:
1. Company-wide workforce overview
2. Recruitment and Attrition Analysis
3. Performance and Attendance Analysis

**Target audience**

* **Leadership**: Gain a high-level  view of workforce size, stability, and department level outliers to guide strategic decisions.
* **HR Director**: Understand where turnover and hiring inefficiencies are concentrated to prioritize retention and recruitment efforts.
* **Department Heads**: Track attendance, performance, and risk signals within their teams to take timely, targeted action.

**Business questions**

* **Workforce:** Is our headcount growing, shrinking, or flat, and where is it concentrated?
* **Attrition:** Which departments, age groups, and tenure segments are most at risk of resigning?
* **Recruitment:** How long does hiring take, and which sources perform best?
* **Attendance:** Is lateness or overtime a real problem, and where does it concentrate?
* **Performance:** Which departments underperform, and does training actually improve results?
* **Employee Level:** Which individual employees show risk signals that need manager attention?

**Project outcome**

The project provided insights into **Performance**, **Attendance** and **Retention** of company key improvement areas to optimize operations

**Key results:**
* Poor ratings performance are widespread, and Operations is the outlier.
* Attrition is concentrated in 2+ year employees, young staff, and the HR and Marketing departments.
* Lateness is company-wide but minor, and overtime is not a problem.
* Hiring time is steady, and training does not improve performance.

---
## 2. Dataset Description & Data Structure
**Data source**
* **Source**: 
* **Size**: Excel file **Flat_HR_workforce** contains 20,000 records
* **Format**: Flat excel file

**Data structure and Relationship**

**Table use**

Datasets consists of 4 tables used to build the dashboard:

<details> 
   <summary> <b>Table 1: Employee data</b></summary>

| Column name | Description |
| ----------- | ----------- |
|`EmployeeID` | Text |
|`Employee Name` | Text|
|`Gender`| Male or Female|
|`Age`| Number|
|`Department` | Linked to department|
|`Position`| position in company|
|`Manager`| Main report to manager|
|`HireDate`| Date|
|`TenureYear` | Number|
|`EmployeeStatus`| Active or Resigned|
|`RecruitmentSource`| Text|
|`RecruitmentDate`| Number| 
|`Salary`|Number|
|`ResignedFlag` | Resigned (1), not resigned (0)|
|`ResignedDate` | date|
|`ResignedReason` | Text|

</details>

<details> 
   <summary> <b>Table 2: Performance</b></summary>

| Column name | Description |
| ----------- | ----------- |
|`ReviewID` | Foreignkey |
|`Reviewdate` | Date|
|`EmployeeID`| Linked to employee|
|`PerformaceScore`| Number|
|`PerformanceRating` | Poor, Good, Average, Excellent|
|`TrainingHours`| number|

</details>

<details> 
   <summary> <b>Table 3: Department</b></summary>

| Column name | Description |
| ----------- | ----------- |
|`DepartmentName` | Foreignkey |

</details>

<details> 
   <summary> <b>Table 4: Attendance</b></summary>

| Column name | Description |
| ----------- | ----------- |
|`EmployeeID` | Linked to employee |
|`Attendancedate` | Date|
|`Workinghours`| Number|
|`LateMinutes`| Number|
|`OvertimeHours` | Poor, Good, Average, Excellent|
|`AbsentFlag`| Absent (1), Not absent (0)|

</details>

**Data Relationship**

## 3. Design Thinking Process

![](/Screenshot/1.jpg)
![](/Screenshot/2.jpg)
---
## 4. Key Insights & Visualization
**Dashboard Review**

### 1. Workforce Overview 
![Workforce Overview](/Screenshot/Overview.png)


**Key finding**

**1. In general**, the company has 1,500 total employees on record, of which 1,408 remain active and 92 have resigned. The organization added 151 new hires. 

--> *Indicating continued hiring activity to replace the resignation levels*.

**2. Headcount Trend:** Headcount has fluctuated significantly, starting at 223 in 2018, dropping sharply to a low of 172 in 2019. The headcount then not change a lot in the amount approximately 180 employee

--> *This is a great point see the decrease in 2018 was might be layoff employee during the Covid-19 Pandemic.* 

**3. Department Distribution:** IT (216) and HR (209) are the two largest departments, followed by Sales (194), Customer Service (190), Supply Chain (180), and Finance (177). 

--> *The spread across departments is fairly even, no single department dominates headcount, which suggests **balanced organizational structure** rather than being top-heavy in one function.*

**4. Position/Level Distribution:** Manager is the most common level (328), followed by Senior (312), Leader (302), Staff (286), and Supervisor (272). 

--> *the structure is top-heavy, and the flat distribution is unusual for a real company.*

**5. Tenure** looks uniform across departments. Every department shows an average tenure clustered right around 5 years, with little visible variation.


**6. Gender Distribution:** The workforce is almost perfectly balanced, 751 Female (50.07%) vs. 749 Male (49.93%).

--> *This is a positive, well-balanced signal with no notable gender skew at the company-wide level.*

--- 
### 2. Attendance Analysis

![Attendance Analysis](/Screenshot/Attendance.png)

**1. Overall** attendance looks healthy at a glance, but the Late Arrival Rate tells a different story. Absent Rate is low (3%) and Attendance Rate is high (97%), which on the surface looks strong. However, There are 60% of employee late for 15 minutes which meaning 

--> *The majority of recorded check-ins involve some lateness.*

**2. Late Arrival Rate**: The Year trend shows a dip around 2020–2021 (~58%) followed by a rise back to ~61% by 2023, then a slight decline again.

--> * The over time is volatile, not steadily worsening*

**3. Lateness** is fairly consistent across departments, not concentrated in one. Late Arrival Rate by Department ranges narrowly from 59% (HR) to 62% (Finance) a spread of only ~3.4 percentage points. 

--> *Confirms lateness is genuinely spread across departments rather than being one team's problem*

**4. Thursday is the clear worst day for lateness.** The Weekday chart shows a sharp peak on Thursday (~61%), with Tuesday as the best day (~60%). 

**Average overtime hours by department** show a tight, compressed range across the period, roughly 1.83 to 2.15 hours,  visualized using a color gradient (white = lowest, pink = highest). 

--> *This narrow spread indicates that overtime is not concentrated in or dominated by any single department*

--> *No department consistently stands out as a persistent outlier. Overtime spikes are likely tied to temporary, year-specific factors (e.g., seasonal workload, project deadlines, short-term staffing gaps) rather than a structural or department-wide overtime problem.*

---
### 3. Attrition & Recruitment Analysis

![Attrition & Recruitment](/Screenshot/Recruitment%20&%20Attrition.png)

**Key finding**

**1. Overall attrition rate** (2.27%) looks low, but hides a strong tenure-based concentration. While the headline attrition rate is modest, the tenure breakdown reveals resignations are concentrated among longer-tenured employees (2-5 years: 55.79%, +5 years: 44.21%) 

**2. Department attrition** is led by HR & Marketing (3.25% and 2.18%), with IT the lowest (1,39%).

**3.Tenure concentration** remains the standout finding. 55.79% of resignations come from the 2-5 year group, with the remaining 44.21% from +5 years. 

--> *Resignations shown come from employees with 2+ years of tenure*. 

**4. Younger employees (under 25) show the highest attrition rate** (3.85%), declining steadily with age the 36-45 group is far more stable (1,90%). 

--> *This suggests early-career retention is a bigger risk than late-career retention.*

**5. Recruitment Time and Hired Source are both fairly flat.** Recruitment time ranges narrowly (49-52 days) across all sources, and hiring source volume (243-264) is evenly distributed across Internal, Referral, Campus, Agency, JobStreet, and LinkedIn no single channel dominates or drags down hiring speed.

**6. Hire time:** Two low points stand out around September-October (119, 119) 

### 4. Performance Analysis

![Performance](/Screenshot/Performance.png)

**Key finding**

**1. Average Performance Score**: 72 

--> *Suggests generally acceptable performance but with real room for improvement.*

**2. High Performance:** Only about 1 in 15 reviews qualifies as high-performing (Excellent)  

--> *Signals that "exceptional performance" is rare in this organization, which has implications for succession planning and internal promotion pipelines.*

**3. Low Performance:** Nearly a third of all reviews fall into the Poor category. This is the most concerning number on the page. It's 4.5x larger than the High Performer group, and represents a substantial share of the workforce.

**4. Performance Distribution** Average (41.52%) is the largest slice, followed by Poor (30.28%), Good (21.43%), and Excellent (6.78%). This chart sets the frame for the whole page: performance is concentrated in the lower half of the scale (Average + Poor = 71.8% combined), while the upper half (Good + Excellent = 28.2%) is comparatively small.

**5. Performance By Position**: Within each Performance Rating bucket, how the 5 position levels (Leader, Manager, Senior, Staff, Supervisor) are represented. 

--> *This show that underperformance is not a "junior staff problem," it cuts across seniority levels, which has different management implications than if it were concentrated at one level.*

**Department Rating Table**:

- **Operations is a clear outlier**: only 24 Excellent ratings (vs. 169-225 everywhere else) and the highest Poor count (1,028) of any department, despite not having the most total reviews (2,370, actually mid-pack). 

   --> *This means Operations' rate of poor performance is unusually high, not just its raw count.*
- **IT has the most total reviews (2,841)** and a relatively strong Excellent count (225, the highest), suggesting 

   --> *IT may have both scale and quality.*
- **Marketing has the fewest total reviews (2,135)** and a middling profile across all categories, no particular strength or weakness stands out.

**Performance Score and Training Hour Scores** across all 4 training buckets are nearly identical: 72, 72, 72, 71. This is a clear, 

--> *Confirmed finding training hours show no meaningful relationship with performance score*. 

---
## 5. Final conclusion and Recommendation
| Aspect | Insight | Recommendation |
|---|---|---|
| **Attendance: policy** | The 60% late rate is spread evenly across departments | Review lateness by department, frequency, and average minutes late, then communicate a clear attendance policy and expected start time. HR can launch a **30-day attendance improvement program**, with managers reminding employees and HR monitoring the results. |
| **Attendance: repeat cases** | A small group may be late repeatedly | Use a progressive approach: **coaching → verbal/written warning → final warning → further disciplinary action**, following company policy and applicable labor law. |
| **Attendance: Thursday** | Thursday is the peak day for lateness | Hold a root-cause conversation with managers: is there a recurring Thursday event (early meeting, different shift pattern, post-Wednesday fatigue)? If it's structural, fix the schedule. |
| **Attrition: tenure** | All resignations come from the 2-5 year (55.79%) and 5+ year (44.21%) groups, and under-25s resign most (3.85%) | Introduce a **2-5 year retention program** with career-path discussions, promotion opportunities, skills training, mentoring, and a stay interview around the 2-year mark. Review salary, benefits, and market competitiveness for this group, since employees may leave when they have the experience but see limited growth internally. |
| **Attrition: departments** | HR (3.35%) and Marketing (3.18%) have the highest attrition, versus IT (1.39%) | For the **HR and Marketing teams**, run focused exit interviews and manager/team-level analysis to find out why attrition is about 2.4x higher than IT. Possible solutions: workload review, shift/scheduling improvements, manager training, recognition programs, and clearer career progression. |
| **Performance: low performers** | 30.28% of reviews are rated Poor, and Operations has only 24 Excellent ratings | For employees with persistent poor performance, use individual **Performance Improvement Plans (PIPs)** with clear targets, timelines, coaching, and consequences. |
| **Performance: training** | Scores are flat (72, 72, 72, 71) whether someone got under 10 or over 30 training hours | **Redesign the training approach rather than simply increasing training hours.** Identify the specific skills causing poor results and replace generic training with **role-specific, practical coaching and on-the-job support**, especially in Operations. |
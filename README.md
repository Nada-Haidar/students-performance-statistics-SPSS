# students-performance-statistics-SPSS
Statistical analysis of student performance using SPSS: t-tests, descriptive statistics, effect sizes, and visualizations.

This project uses the **Students Performance in Exams** dataset to explore how a **test preparation course** affects students' math achievement.  
All analyses were conducted in **IBM SPSS Statistics**.

---

## 🎯 Research Question

> Do students who completed the test preparation course score higher in math than students who did not complete the course?

---

## 📊 Dataset

- **Source:** StudentsPerformance.csv (Kaggle – Students Performance in Exams)
- **Sample size:** 1,000 students  
- **Key variables used:**
  - `mathscore` – math exam score (0–100)
  - `readingscore` – reading exam score (0–100)
  - `writingscore` – writing exam score (0–100)
  - `testpreparationcourse` – *completed* / *none*
  - `gender`, `parentallevelofeducation`, `lunch`, `raceethnicity`

---

## 🧪 Methods

All analyses were performed in **SPSS**:

1. **Data import & cleaning**
   - Imported `StudentsPerformance.csv` into SPSS.
   - Saved working file as `studentsperformance.sav`.
   - Checked variable types (string vs numeric).

2. **Descriptive statistics**
   - Calculated N, minimum, maximum, mean, and standard deviation for:
     - `mathscore`
     - `readingscore`
     - `writingscore`

3. **Frequencies & bar charts**
   - Frequency tables and bar charts for:
     - `gender`
     - `testpreparationcourse`

4. **Recoding for analysis**
   - Created a new numeric grouping variable:
     - `test_prep`  
       - `1 = completed`  
       - `0 = none`

5. **Independent Samples T-test**
   - Test variable: `mathscore`
   - Grouping variable: `test_prep` (1 vs 0)
   - Assessed:
     - Equality of variances (Levene’s test)
     - Difference in mean math scores
     - Statistical significance (p-value)
     - Effect size (Cohen’s d)

---

## 📈 Key Results

### Group Descriptives

| Group (test_prep) | Description                     | N   | Mean math score | Std. Deviation |
|-------------------|---------------------------------|-----|-----------------|----------------|
| 1                 | Completed prep course           | 358 | **69.70**       | 14.45          |
| 0                 | No prep course                  | 642 | **64.08**       | 15.19          |

Students who completed the preparation course scored about **5.62 points higher** in math on average.
---

### Independent Samples T-test

Using the “Equal variances assumed” row:

- **t(998) = 5.71**  
- **p < .001** (two-tailed)  
- **Mean difference = 5.62**  
- **95% CI for difference: [3.69, 7.55]**

**Interpretation:**  
The difference in math scores between students who **completed** the test preparation course and those who **did not** is **statistically significant**. Students who took the course performed better in math.

---

### Effect Size

- **Cohen’s d ≈ 0.38**

**Interpretation:**  
Effect size is in the **small-to-medium** range, suggesting the preparation course has a meaningful positive impact on math performance.

---

## 🛠 How to Reproduce the Analysis in SPSS

1. **Open data**
   - `File → Open → Data…`  
   - Select `StudentsPerformance.csv`

2. **Descriptive statistics**
   - `Analyze → Descriptive Statistics → Descriptives…`
   - Add `mathscore`, `readingscore`, `writingscore`
   - Request mean, std. deviation, min, max.

3. **Frequencies & bar charts**
   - `Analyze → Descriptive Statistics → Frequencies…`
   - Add `gender`, `testpreparationcourse`
   - Check **Display frequency tables**
   - For bar charts: `Graphs → Legacy Dialogs → Bar… → Simple`

4. **Create numeric prep variable**
   - `Transform → Recode into Different Variables…`
   - Old variable: `testpreparationcourse`
   - New variable: `test_prep`
   - Old and New Values:
     - "completed" → 1
     - "none" → 0

5. **Run Independent Samples T-test**
   - `Analyze → Compare Means → Independent-Samples T Test…`
   - Test Variable: `mathscore`
   - Grouping Variable: `test_prep`
   - Define Groups: Group 1 = 1, Group 2 = 0

---

## 📁 Project Structure

Suggested file structure for this repository:

```text
students-performance-statistics-spss/
│── README.md
│── StudentsPerformance.csv
│── studentsperformance.sav
│── output/
│    └── ttest_mathscore.spv
│── graphs/
│    ├── gender_bar_chart.png
│    ├── testprep_bar_chart.png
│    └── mathscore_boxplot_by_testprep.png
│── report/
     └── student_performance_report.pdf
👤 Author

Name: Nada Haidar

Program/Institution: MESA – University of Illinois Chicago (UIC)

Tools: SPSS, Excel, GitHub

Focus: Applied statistics and data analysis portfolios.

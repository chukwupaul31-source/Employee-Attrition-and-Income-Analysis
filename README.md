 # 👨‍💼Employee Attrition and Income Analysis

 ##  💼Project Summary
This project "Employee Attrition and Income Analysis," utilizes SQL queries to perform a deep-dive examination of employee data, focusing on attrition patterns, income distribution, and performance-related metrics within an HR dataset. The methodology moves from foundational data exploration to advanced techniques like Common Table Expressions (CTEs), subqueries, and Window Functions (LAG, LEAD, RANK). The analysis identifies key factors associated with income and tenure, ultimately providing actionable insights for talent management and retention strategies. This project serves as a robust example of leveraging SQL for strategic HR analytics to uncover complex relationships and trends in organizational data
The main goal is to help HR teams understand employee behavior, pay fairness, and performance trends across departments.

## 🧠Methodology and Structure
The project employs a structured, multi-step analytical methodology, detailed across 12 distinct SQL queries, demonstrating a progression of complexity and insight:
### Foundational Data Manipulation
- Data Retrieval and Filtering (Queries 1, 2): I Began my  analysis  with standard SELECT * for initial exploration, followed by complex multi-condition filtering using NOT IN, AND, and OR to segment the employee population based on attrition status, department, and education. This ensures the ability to target specific subsets of interest.
- Aggregation and Subqueries (Queries 4, 5, 6): I used standard aggregation functions (SUM, AVG, MAX) with GROUP BY and introduced a CTE (Query 4) for modular, staged analysis of income per job role. Queries 5 and 6 applied HAVING clauses and nested subqueries to find departmental maximums and employees with minimum income, respectively.
Advanced Analytical Techniques
- Window Functions (Queries 8, 9, 11):The project leverages:
LEAD() and LAG() (Queries 8, 11) for time series-like comparison (or sequence comparison based on specified partitions and orders), effectively tracking "Performance Trends" by comparing an employee's current MonthlyIncome to the next or previous record's income within partitions (by Age or Education).
RANK() (Queries 9, 12) to calculate the rank of employees based on MonthlyIncome, a crucial metric for compensation analysis.
- Case Logic and Conditional Analysis (Queries 8, 10, 12): I make Used  of the CASE statements and the IF() function to classify and categorize data, for example, classifying employees as 'High' or 'Low' income based on predefined thresholds.
- Cross-Row Calculation (Query 7):  I Utilized correlated subqueries to append company-wide MAX, MIN, and AVG income to every individual employee record, providing immediate context for how an employee's salary compares to the overall distribution.

## 💡Key Findings
The queries performed suggest the following key findings, which form the basis for strategic recommendations:
- Income Extremes and Distribution: Queries 6 and 7 efficiently identified the minimum and maximum income earners. Query 4, using the CTE, quickly surfaces job roles that command the highest maximum salaries, indicating key executive or highly specialized roles are concentrated in the top 10 maximum incomes.
- Attrition and Filtering Complexity: Query 2 demonstrates that the most relevant cohort for complex analysis (e.g., non-attrition, certain departments, high education) can be isolated through advanced filtering, which is the necessary first step for predicting retention.
- Income Mobility and Trends: The LEAD() and LAG() analysis (Queries 8, 11) provides a simulated look at income progression or comparison. The resulting Performance_Trend column (e.g., 'Improved,' 'Declined,' 'Stable') is a powerful, easily interpretable derived metric that highlights income momentum or stagnation within specific partitions (e.g., by age or education level).
- Performance and Tenure Relationships: Query 3 connects job role, tenure (YearsAtCompany), and performance rating. The filtering targets employees outside of major roles (Sales Executive, Research Scientist) or those with short tenure/high experience, suggesting a focus on mid-career, specialized employees where performance gaps might be most critical.

## 🧰Key Features Of The Projects

The project demonstrates expertise across several high-value SQL capabilities essential for strategic data analysis:
- Advanced Sequence Analysis with Window Functions: The project extensively leverages Window Functions such as LAG(), LEAD(), and RANK(). This skill is crucial for deriving cross-row comparisons (like income comparisons over sequence) and calculating relative performance metrics without resorting to complex self-joins. Specifically, LAG() and LEAD() enable a simulated look at income progression, resulting in the creation of the easily interpretable 'Performance_Trend' metric.
- Modular Query Development with CTEs: The use of Common Table Expressions (CTEs) demonstrates proficiency in structuring complex queries. This technique promotes query modularity, significantly improving readability and aiding in the staging of multi-step analyses, such as initial income aggregation before final filtering.
- Targeted Data Retrieval and Extremes: Mastery of Nested Subqueries and the HAVING clause is shown by efficiently identifying employees with extreme values (e.g., minimum monthly income) and filtering aggregated results (e.g., departments meeting a minimum income threshold).
- Data Transformation using Conditional Logic: The project utilizes both the standard CASE statement and the MySQL-specific IF() function to implement conditional logic. This enables robust data classification and the creation of easily digestible business metrics (e.g., classifying income as 'High' or 'Low' and trend as 'Improved' or 'Declined').
- Precise Population Segmentation: Expertise in Complex Filtering using sophisticated combinations of AND, OR, and NOT IN is evident. This capability is vital for the precise isolation of target populations based on multiple criteria (like attrition status, department, and education level), which is a prerequisite for focused HR interventions.

## 🧰 Tools & Technology
Database: MySQL
Techniques Used: Window Functions, CTEs, Subqueries, Conditional Logic, and Complex Filtering
Data Source: Employee and departmental HR dataset
Focus Areas: Income analysis, performance tracking, and workforce segmentation.

## 🧠Recommendations.

Based on my  analytical foundation built by the SQL queries, the following actionable recommendations can be made to improve talent management and retention.
- High-Level Compensation Review: Standardize salary bands for the top-earning Job Roles identified in Query 4. The wide variance in maximum incomes suggests a need to ensure internal equity and market competitiveness for critical positions to prevent attrition among high-value talent.
- Targeted Retention Programs: Focus retention efforts on the "Declined" income trend cohort identified by the LEAD/LAG functions (Queries 8, 11). These employees, regardless of age or education, are statistically more likely to feel undervalued or stagnant and may be at a higher risk of leaving.
- Investigate Low-Income Cohort: Conduct exit interviews or salary benchmarks for employees identified with MonthlyIncome below the company-wide average (identified in Query 7) and those in the 'Low' category (Query 10). If the low income is not market-competitive, adjust compensation to prevent involuntary turnover due to financial reasons.
- Performance and Tenure Analysis: Investigate the specific cohort filtered in Query 3 (specialized roles, low company tenure, but high total working years). These are often experienced external hires. Ensure their performance is on track, as a mismatch could indicate a poor fit leading to early attrition.

NOTE I SAVED AND UPLOAD THE QUERY USING JUPYTER NOTEBOOK[CLICK THE ABOVE LINK IN THE BRACKET TO VIEW THE QUERY] 
(https://github.com/chukwupaul31-source/HR-Analytics-with-SQL-/blob/main/HR%20Analytics%20SQL%20Project.ipynb)

# Stack Overflow Developer Survey Analysis: Unlocking Career & Well-being Insights

## Project Overview

This project delves into a rich dataset from the annual Stack Overflow Developer Survey to uncover fascinating insights into the global developer community. By applying a robust data science workflow, from meticulous data cleaning to advanced hypothesis testing, this analysis explores key questions surrounding developer compensation, job satisfaction, the impact of experience and education, and considerations of pay equity.

This repository serves as a practical demonstration of end-to-end data science skills, making it an ideal showcase for a data science portfolio.

## Problem Statement & Motivation

The Stack Overflow Developer Survey collects a vast amount of self-reported data, which, while incredibly valuable, often comes with inherent challenges like missing values and complex data structures. The motivation behind this project was twofold:

1.  To extract meaningful, actionable insights from this complex dataset regarding developer career progression and well-being.
2.  To demonstrate a strong command of critical data science methodologies, including data preprocessing, exploratory data analysis, statistical hypothesis testing, and effective communication of findings.

## Dataset

The core of this project is the **Stack Overflow Developer Survey dataset**. This comprehensive survey captures a wide array of information about developers globally, including:

  * **Demographics:** `age`, `country`, `gender`, `ethnicity`, `edlevel` (education level)
  * **Professional Background:** `mainbranch`, `devtype` (developer type), `yearscode`, `yearscodepro` (years of professional coding experience), `employment`, `orgsize`
  * **Compensation:** `comptotal`, `convertedcomp` (annual compensation converted to USD), `compfreq`
  * **Job Satisfaction & Factors:** `jobsat`, `jobfactors`, `workweekhrs`
  * **Technologies:** `languageworkedwith`, `languagedesirenextyear`, `webframeworkedwith`, `platformworkedwith`, `databaseworkedwith`, etc.
  * **Survey Engagement:** `soaccount`, `sovisitfreq`, `socomm`

## Key Questions & Hypotheses Explored

This project rigorously investigates several core hypotheses:

1.  **Compensation & Experience:**

      * **Hypothesis:** Is there a significant positive correlation between a developer's professional coding experience (`yearscodepro`) and their annual compensation (`convertedcomp`)?
      * **Analysis:** Pearson Correlation Test.

2.  **Job Satisfaction & Work-Life Balance:**

      * **Hypothesis:** Do developers working significantly above or below average `workweekhrs` report different levels of `jobsat` (job satisfaction) compared to those working average hours?
      * **Analysis:** Categorization of work hours, Chi-squared Test of Independence.

3.  **Gender Pay Equity:**

      * **Hypothesis:** Is there a statistically significant difference in `convertedcomp` across different `gender` identities within the developer community?
      * **Analysis:** Pairwise t-tests with Bonferroni correction (as a preliminary step, acknowledging the need for multivariate control).

4.  **Education Level & Compensation:**

      * **Hypothesis:** Is there a statistically significant difference in `convertedcomp` across different `edlevel` (Educational Level) within the developer community?
      * **Analysis:** Pairwise t-tests with Bonferroni correction.

## Methodology & Skills Demonstrated

This project showcases a comprehensive data science pipeline:

1.  **Data Acquisition & Understanding:**

      * Initial inspection of raw survey data, identifying complex structures and missingness patterns (e.g., using `missingno` library).

2.  **Robust Data Cleaning & Preprocessing:**

      * **Missing Value Imputation:** Strategically handled missing data using **K-Nearest Neighbors (KNN) Imputation** from `fancyimpute`, a sophisticated method that preserves data relationships better than simple imputation or deletion.
      * **Data Type Conversion:** Ensured all columns (`age`, `yearscodepro`, `convertedcomp`, etc.) were correctly typed for numerical analysis.
      * **Feature Engineering & Categorization:** Transformed continuous variables (e.g., `workweekhrs` binned into 'Below Median', 'Around Median', 'Above Median') for comparative analysis.
      * **Multi-Select Column Handling:** Addressed complex string-based columns (`languageworkedwith`, `devtype`) by parsing and conceptualizing one-hot encoding for future detailed analysis.
      * **Categorical Encoding:** Prepared nominal and ordinal categorical variables for statistical tests.

3.  **Exploratory Data Analysis (EDA):**

      * Extensive use of descriptive statistics to understand variable distributions.
      * Creation of various visualizations (scatter plots, box plots, stacked bar charts, `missingno` matrix) to uncover initial patterns, outliers, and relationships.

4.  **Statistical Hypothesis Testing:**

      * **Formulated Clear Hypotheses:** Defined null and alternative hypotheses for each research question.
      * **Assumption Checks:** Implicitly, prior to tests, an understanding of underlying assumptions (normality, homogeneity of variance, independence) was considered for appropriate test selection.
      * **Diverse Statistical Tests:** Applied a range of tests:
          * **Pearson Correlation:** To quantify linear relationships.
          * **Chi-squared Test of Independence:** To assess associations between categorical variables.
          * **Pairwise t-tests with Bonferroni Correction:** To compare means across multiple groups while accounting for multiple comparisons.
      * **Rigorous Interpretation:** Drew conclusions based on p-values and statistical significance, critically discussing implications and limitations.

5.  **Critical Analysis & Future Work:**

      * Highlighted nuances in findings (e.g., the counter-intuitive results for education and gender pay gap in simple pairwise tests).
      * Identified the need for more advanced techniques (e.g., multiple regression) to control for confounding variables and gain deeper, multivariate insights into complex relationships.

## Key Findings (Summary)

  * A **statistically significant positive correlation** was found between professional coding experience and annual compensation.
  * There is a **highly significant association** between the number of hours worked per week and job satisfaction, suggesting work-life balance plays a crucial role.
  * In the **preliminary pairwise analyses**, no statistically significant differences in compensation were found across specific `gender` identities or `edlevel` categories after Bonferroni correction. This underscores the complexity of pay equity and the need for **multivariate analysis** to control for other influencing factors (e.g., experience, country, specific technologies).

## Technologies Used

  * **Python:** The primary programming language for analysis.
  * **Pandas:** For data manipulation and analysis.
  * **NumPy:** For numerical operations.
  * **Matplotlib & Seaborn:** For data visualization.
  * **Scipy:** For statistical functions (e.g., Pearson correlation).
  * **Pingouin:** For comprehensive statistical tests (e.g., Chi-squared, pairwise t-tests).
  * **FancyImpute:** Specifically `KNN` for robust missing value handling.

## How to Run the Project

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/your-repo-name.git
    cd your-repo-name
    ```
2.  **Install dependencies:**
    It's recommended to use a virtual environment.
    ```bash
    pip install -r requirements.txt
    ```
    (You'll need to create a `requirements.txt` file from your environment, e.g., `pip freeze > requirements.txt`)
3.  **Download the dataset:**
    The Stack Overflow Developer Survey data can typically be found on Kaggle (e.g., for the relevant year, 2020 or 2019, depending on your data). Place the CSV file in a `data/` directory within the project root.
4.  **Run the Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```
    Open `developer_survey_analysis.ipynb` (or whatever your notebook is named) and run the cells sequentially.

## Contact

Feel free to connect with me for questions, feedback, or collaborations\!
iordyebarnabas12@gmail.com
-----

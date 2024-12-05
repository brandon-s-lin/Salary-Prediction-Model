# Final Project Problem Statement & Approach

---

### Problem Statement

**Objective:** Develop two predictive models to estimate an individual’s salary based on selected personal and professional attributes.  
**Target Variable:** **Salary** (continuous)  
**Features:** **Age**, **Education Level**, **Years of Experience**  

The goal is to identify a relationship between these features and the salary, thereby enabling more accurate salary predictions for individuals.

---

### Approach Overview

The solution involves applying supervised machine learning regression techniques. The approach includes comprehensive data preprocessing, feature engineering, model selection, and thorough evaluation. By focusing on a small but meaningful set of features—Age, Gender,Education Level, Job Title, and Years of Experience—the aim is to create a model that is both interpretable and reasonably accurate.

---

### Detailed Step-by-Step Approach

#### 1. Problem Understanding
- **Context:** I wanted to predict a continuous variable (Salary) from a couple hand selected input features: Age, Education Level, and Years of Experience.
- **Justification for Feature Choice:**  
  - **Age**: Often correlates with experience and career stage.  
  - **Education Level**: Higher education may correlate with higher-paying roles.  
  - **Years of Experience**: Strongly linked to skill depth and salary progression.
- **Feature Exclusions:**  
  - **Job Title** was removed due to its complexity and lack of clear relevance after preliminary inspection. It might introduce unnecessary categorical complexity and does not directly enhance performance based on initial hypotheses.

#### Data Preprocessing
- **Handling Missing Values:** Rows with missing Age, Years of Experience, or Salary values were dropped to ensure data quality.  
- **Type Conversions:** Converted Age, Years of Experience, and Salary to integers for easier interpretation, analysis, and visualization.  
- **Standardization and Encoding:** Standardized or normalized the Education Level feature and converted categorical/string data into numerical codes to ensure compatibility with modeling algorithms. Also standardized the Age, Years of Experience, and Salary columns by setting the mean to 0 and the standard deviation to 1. This step helps models to process inputs more efficiently and consistently.

---

#### 2. Data Exploration
- **Descriptive Statistics:** Examined mean, median, and IQRs to understand the structure and correlation.
- **Visualizations:** Created histograms to check the distribution of numerical features; boxplots, bar graphs, and scatter plots helped identify outliers and potential relationships (e.g., how Salary trends with Years of Experience).
- **Correlations:** Used heatmaps to gauge the strength and direction of relationships between features (e.g., does more experience strongly correlate with higher salary?).

---

#### 3. Feature Selection & Engineering
- **Initial Feature Set:** Age, Education Level, Years of Experience (post-encoding and cleaning).
- **Rationale:** These features strike a balance between complexity and explanatory power.  
- **Iterative Refinement:** Considered removing or transforming features based on preliminary model performance. For instance, tested models with and without Education Level to see if it genuinely improves predictions.

---

#### 4. Model Selection and Training
- **Baseline Model – Ridge Regression:**  
  - **Purpose:** Establish a simple reference point for performance.  
  - **Rationale:** Ridge Regression is a fast, easily interpretable model that provides insights into the linear relationships between features and Salary.
  
- **Advanced Model – Random Forest Regressor:**  
  - **Purpose:** Capture non-linear patterns, interactions, and complex relationships that linear models might miss.  
  - **Rationale:** Tree-based models like Random Forests are robust to outliers, handle mixed feature types well, and often outperform linear models on complex real-world data.

- **Training Process:**  
  - Split data into training and testing sets to avoid overfitting and to fairly assess generalization performance.  
  - Manually tuned hyperparameters (e.g., number of trees, maximum depth in Random Forest) to find the best-performing model configuration.

---

#### 5. Model Evaluation
- **Metrics:**  
  - **Mean Absolute Error (MAE):** Indicates how much, on average, our predictions differ from the actual salaries.  
  - **Mean Squared Error (MSE):** Penalizes larger errors more, helping refine models that sometimes produce large inaccuracies.  
  - **R² Score:** Measures how much of the variance in Salary is explained by the model’s features.

- **Interpretation:**  
  - Lower MAE and MSE values indicate better predictive accuracy.  
  - Higher R² suggests that our chosen features and model explain the variance in Salary well.

- **Comparative Analysis:**  
  Compare the performance of the baseline (Linear Regression) and the advanced model (Random Forest) to confirm if the latter provides a meaningful improvement.

---

### Conclusion and Next Steps

- **Summary:** After data cleaning, feature selection, and experimentation with regression models, the Random Forest Regressor provided better Salary predictions than the baseline Ridge Regression model.

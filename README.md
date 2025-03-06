# World Happiness Index Analysis

## Overview

This project explores and analyzes the World Happiness Index dataset using Python to identify patterns, trends, and insights into the factors that contribute to happiness on a global scale. The analysis covers data from 2005 to 2023, considering approximately 165 countries and various socioeconomic variables.

## Data Source

[World Happiness Report Data](https://worldhappiness.report/data/)

The World Happiness Report is a landmark survey of the state of global happiness. This study uses data available at the provided link.

## Variables

The following variables were considered in this study:

-   **Country Name:** Name of the country.
-   **Year:** Year of the observation.
-   **Life Ladder:** Happiness score, representing the best possible life (top of the ladder) to the worst (bottom of the ladder).
-   **Log GDP Per capita:** GDP per capita in purchasing power parity (PPP) at constant international dollar prices.
-   **Social Support:** Indication of whether individuals have someone to count on in times of need.
-   **Healthy Life Expectancy at Birth:** Expected age of a child at birth.
-   **Freedom to make Life Choices:** National average of responses to the question: "Are you satisfied or dissatisfied with your freedom to choose what you do with your life?"
-   **Generosity:** National average of responses to the question: "Have you donated money to a charity in the past month?" on GDP per capita.
-   **Perceptions of Corruption:** National average of survey responses to questions about the prevalence of corruption in government and businesses.
-   **Positive Effect:** Average of three positive affect measures: laugh, enjoyment, and doing interesting things.
-   **Negative Effect:** Average of three negative affect measures: worry, sadness, and anger.

## Mission Objectives

-   Identify the average happiness across all years in all countries.
-   Determine the top 10 happiest and bottom 10 least happy countries.
-   Analyze the correlation between variables that define a country's happiness.
-   Predict the happiness of a country using machine learning.

## Data Cleaning

The following steps were taken to clean the data:

1.  **Duplicate Removal:** Verified and ensured the absence of duplicate entries.
2.  **Year Filtering:** Removed data from 2005 and 2006 due to limited data.
3.  **Country Filtering:** Excluded countries with less than 10 years' worth of data.
4.  **Missing Value Identification:** Used `isna()` to identify NaN values in each column.
5.  **Missing Value Imputation:** Imputed missing values with country-specific mean values.
6.  **Post-Imputation Validation:** Identified columns with entirely NaN values after imputation.
7.  **Row Removal:** Dropped rows associated with countries having NaN values that couldn't be imputed accurately.
8.  **Consistency:** Eliminated any remaining missing or duplicate values.

## Exploratory Data Analysis (EDA)

### Descriptive Statistics

Descriptive statistics for the variables:

|                 | year         | Life Ladder | Log GDP per capita | Social support | Healthy life expectancy at birth | Freedom to make life choices | Generosity | Perceptions of corruption | Positive affect | Negative affect |
| :-------------- | :----------- | :---------- | :----------------- | :------------- | :----------------------------- | :--------------------------- | :--------- | :------------------------ | :-------------- | :-------------- |
| **count**       | 1896.000000  | 1896.000000 | 1896.000000        | 1896.000000    | 1896.000000                    | 1896.000000                  | 1896.000000 | 1896.000000               | 1896.000000     | 1896.000000     |
| **mean**        | 2014.663502  | 5.525224    | 9.442846           | 0.812467       | 63.836927                      | 0.749804                     | -0.002600   | 0.739999                  | 0.652260        | 0.273770        |
| **std**         | 4.414495     | 1.132399    | 1.131834           | 0.119389       | 6.504014                       | 0.138745                     | 0.160735    | 0.188120                  | 0.107706        | 0.085259        |
| **min**         | 2007.000000  | 1.281000    | 5.527000           | 0.228000       | 17.360000                      | 0.258000                     | -0.338000   | 0.035000                  | 0.179000        | 0.083000        |
| **25%**         | 2011.000000  | 4.669000    | 8.526000           | 0.747750       | 60.130000                      | 0.659000                     | -0.117000   | 0.683000                  | 0.568750        | 0.210000        |
| **50%**         | 2015.000000  | 5.488500    | 9.548000           | 0.839000       | 65.325000                      | 0.770000                     | -0.026000   | 0.797500                  | 0.663000        | 0.265000        |
| **75%**         | 2018.000000  | 6.375000    | 10.424250          | 0.906000       | 69.006250                      | 0.861000                     | 0.091000    | 0.867250                  | 0.739250        | 0.326000        |
| **max**         | 2022.000000  | 7.971000    | 11.664000          | 0.987000       | 74.475000                      | 0.985000                     | 0.703000    | 0.983000                  | 0.884000        | 0.607000        |

### Key Findings from EDA

1.  **Happiness Index Trend:**
    -   Overall positive trend.
    -   Significant increase post-2008 financial crisis.
    -   Decline during the COVID-19 pandemic.

2.  **Happiness vs. Perception of Corruption:**
    -   An inverse relationship between the corruption score and the happiness index.

3.  **Happiness vs. Freedom to Make Life Choices:**
    -   A positive correlation between satisfaction with freedom of choices and the happiness index.

4.  **Happiness vs. Negative Affect:**
    -   An increase in negative affect alongside a rising happiness index, suggesting complex dynamics.

5.  **Top 10 and Lowest 10 Countries:**
    -   The top 10 countries consistently exhibit higher average happiness scores.

6.  **Consistency in Top 10 Rankings:**
    -   Denmark stands out as the most consistent performer in the top 10.

7.  **Correlation Matrix:**
    -   Strong positive relationship between life satisfaction, economic prosperity, and social support.
    -   Perception of corruption is inversely related to these factors.
    -   Autonomy in life choices correlates positively with positive emotions.

8.  **Scatter Plots:**
    -   Positive association between Life Ladder score and Log GDP per capita, Social Support, and Healthy Life Expectancy at Birth.

9.  **Violin Plot:**
    -   The violin plot illustrates the distribution of Happiness Index values for each country across multiple years. It shows the impact of major world events like the economic crisis of 2008 and the COVID-19 pandemic on happiness indices.

## Machine Learning

### Regression Modeling

The following steps were performed for regression modeling:

1.  Defined features (X) and target variable (Y) i.e., Happiness score.
2.  Split the dataset into training and testing sets (80%-20% split).
3.  Trained the model using the training data.
4.  Made predictions on the testing set.
5.  Displayed model outcomes using scatter plots.
6.  Assessed model performance using metrics like Mean Squared Error (MSE) and R-squared value.

### Model Evaluation

Evaluated models using MSE and R-squared score. Lower MSE values and R-squared values close to 1.0 indicate better model performance.

-   **Simple Linear Regression:** R-squared = 0.795, MSE = 0.25
-   **Random Forest Regression:** R-squared = 0.878, MSE = 0.15

Random Forest Regression performed better due to its ensemble nature and ability to avoid overfitting.

### Model Usefulness

The model can be used for:

1.  **Predictive Analytics:** Estimating future happiness scores based on changing conditions.
2.  **Understanding Feature Importance:** Insights into which factors contribute the most to happiness scores.
3.  **Monitoring Changes Over Time:** Tracking changes in happiness trends over time.
4.  **Targeted Interventions:** Targeting specific aspects that have a significant impact on happiness.
5.  **Resource Allocation:** Allocating resources more efficiently by understanding influential factors.

## Conclusion

The analysis reveals that economic output, social frameworks, and health parameters are pivotal in shaping a nation's happiness. Regional disparities are apparent, and regression models effectively predict national happiness levels.

## Recommendations

1.  **Universal Healthcare:** Ensure equitable access to essential medical services.
2.  **Economic Strategies:** Prioritize growth in GDP per capita through investment and infrastructure development.
3.  **Work-Life Balance:** Implement policies that nurture work-life balance, such as flexible working arrangements and parental leave.

# World Happiness Data Analytics Report

## Overview
This repository contains a comprehensive data analytics project investigating the primary drivers behind global happiness levels. The project utilizes World Happiness Report data spanning from 2015 to 2019, combined with corresponding life expectancy statistics, to uncover statistical relationships between critical socioeconomic factors and overall societal happiness.

## Research Questions
The analysis seeks to answer two primary questions:
1. **The Impact of Health:** Do countries with a higher Life Expectancy score (above the global average) have a significantly higher Happiness Score compared to countries with lower life expectancies?
2. **Economic and Social Drivers:** To what extent do GDP per capita and Social Support independently predict a nation's Happiness score?

## Methodology
The project employs several statistical machine learning and hypothesis testing techniques within building the final analytics report:
- **Data Preprocessing & Cleaning:** Aggregating data across 5 different temporal datasets and handling missing/invalid components.
- **Parametric & Non-Parametric Testing:** 
  - Shapiro-Wilk Normality test & Levene's Test for Homogeneity.
  - Wilcoxon Rank-Sum test applied to mitigate non-normal dataset conditions.
- **Predictive Modeling:**
  - Multiple Linear Regression to isolate the individual magnitudes of correlation for independent variables (GDP and Social Support).
  - Polynomial Regression applied to capture curvilinear effects and correct residual imbalances (U-shape fitted vs residual patterns).
  - Variance Inflation Factors (VIF) checked to ensure the absence of widespread multicollinearity.

## Visualizations

Here is a glimpse into the empirical data patterns evaluated during the analysis:

**Normal Q-Q Plot: Happiness Scores by Health Sector**  
![Normal Q-Q Plot: Happiness Scores by Health Sector](images/qq_plot.png)

**Impact of Healthy Life Expectancy on Happiness**  
![Boxplot: Happiness and Life Expectancy](images/boxplot.png)

**Regression Analysis: GDP & Social Support vs Happiness**  
![Regression Models: Economic and Social Variables](images/scatter_plots.png)

## Repository Structure
```
|-- Data/
|   |-- 2015.csv
|   |-- 2016.csv
|   |-- 2017.csv
|   |-- 2018.csv
|   |-- 2019.csv
|-- final_project.Rmd                 # Primary Analytics Report containing analysis, inference, and visualization
|-- final_project.html                # Compiled interactive HTML version of the primary report
|-- happiness_data_cleaning (1).Rmd   # Script handling the initial data cleaning process
|-- happiness_final.csv               # Merged and pre-computed analytical data
|-- gdp_data.csv / life_expectancy_data.csv # Raw metadata components
|-- .gitignore                        # Git configuration to ignore large environment logs
```

## Technologies & Libraries
The entirety of the data analytics pipeline is written in **R**, relying heavily on the following foundational packages:
- `tidyverse` (dplyr, ggplot2, tidyr) for rapid data transformation and visual composition.
- `car` for Levene testing and VIF evaluation.
- `patchwork` for complex plot aggregations.
- `corrplot` for plotting heatmap correlation matrixes.

## How to Reproduce
1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/Rohanpatel91002/World-Happiness-Data-Analytics-Report.git
   ```
2. Open the project within `RStudio` or an equivalent R terminal.
3. Ensure the required packages (listed in the imports above) are installed via `install.packages()`.
4. Render `final_project.Rmd` using the Knitr extension (`Ctrl + Shift + K`) to reproduce the data findings alongside its visual assets. 

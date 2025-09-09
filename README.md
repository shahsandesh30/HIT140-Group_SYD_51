# HIT140 Assessment 2 - Bat and Rat Behavior Analysis

## Project Overview

This project investigates whether bats exhibit avoidance behavior when rats are present at feeding sites, which would suggest that bats perceive rats as a predation risk. The analysis examines two complementary datasets to understand the relationship between rat presence and bat foraging behavior.

## Research Question

**Do bats avoid food sources when rats are present, indicating they perceive rats as a predation threat?**

## Hypothesis

- **Null Hypothesis (H₀)**: Rat presence has no effect on bat landing frequency
- **Alternative Hypothesis (H₁)**: Bats land less frequently when rats are present (indicating avoidance behavior)

## Dataset Description

The project uses two datasets:

### Dataset 1: Individual Bat Landing Events (907 observations)
- `start_time`: landing time (datetime)
- `rat_period_start`, `rat_period_end`: rat presence window (datetime)
- `seconds_after_rat_arrival`: seconds from rat arrival to bat landing (numeric)
- `bat_landing_to_food`: seconds from landing to approaching food (latency)
- `risk`: 1 = risk-taking, 0 = avoided
- `reward`: 1 = obtained food, 0 = did not
- `hours_after_sunset`, `season`, `month`, `sunset_time`: context

### Dataset 2: 30-minute Time Periods (2,123 observations)
- `time`: period start (datetime)
- `bat_landing_number`: # of bat landings in the period
- `rat_minutes`: minutes rats were present in the period
- `rat_arrival_number`: # of rat arrivals in the period
- `food_availability`, `hours_after_sunset`, `month`, `season`: context

## Key Findings

The analysis provides strong evidence that bats reduce their feeding activity in the presence of rats:

- **Avoidance Effect**: Bats landed significantly less often when rats were present (~6 fewer landings per 30 minutes)
- **Statistical Significance**: Welch's t-test shows p < 0.001
- **Dose-Response Relationship**: Negative correlation between rat presence duration and bat activity
- **Consistency**: Effect was robust across seasonal conditions

## Project Structure

```
├── data/
│   ├── dataset1.csv          # Individual bat landing events
│   └── dataset2.csv          # 30-minute observation periods
├── figures/                  # Generated visualizations
│   ├── landings_distribution.png
│   ├── rat_minutes_distribution.png
│   ├── landings_with_vs_without_rats_boxplot.png
│   ├── latency_to_food_distribution.png
│   ├── rat_minutes_vs_bat_landings.png
│   ├── landings_by_rat_minute_bins.png
│   └── landings_by_season_and_rat_presence.png
└── HIT140_Assessment2_BatRat_Objective1.ipynb  # Main analysis notebook
```

## Analysis Methods

1. **Data Cleaning**: Datetime conversion, numeric type conversion, missing value handling
2. **Feature Engineering**: Binary flags, categorical bins, season mapping, ratio metrics
3. **Descriptive Analysis**: Summary statistics and distribution visualizations
4. **Hypothesis Testing**: 
   - Welch's t-test for comparing means
   - Confidence intervals for effect size
   - Chi-square test for categorical associations
   - Pearson correlation analysis
5. **Data Wrangling**: Grouped summaries by rat presence and seasonal patterns

## Technologies Used

- **Python**: Primary programming language
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computations
- **Matplotlib/Seaborn**: Data visualization
- **SciPy**: Statistical testing
- **Jupyter Notebook**: Interactive analysis environment

## Results Summary

**Final Answer**: Yes, bats avoid food sources when rats are present. The analysis shows bats land significantly less often when rats are present (≈6 fewer landings per 30 minutes), with concordant parametric and non-parametric tests and a negative correlation with rat minutes, indicating clear avoidance consistent with perceived predation risk.

## Group Information

This is a group project for HIT140 (Foundation of Data Science) Assessment 2, focusing on Objective 1 of the bat-rat behavior analysis.

## Academic Integrity

This project adheres to Charles Darwin University's academic integrity policies. All analysis and conclusions are based on the provided datasets and standard statistical methods.

---

*For detailed analysis code and results, please refer to the main Jupyter notebook: `HIT140_Assessment2_BatRat_Objective1.ipynb`*

# Statistical Analysis in R

Two statistical analysis assignments written in R Markdown, covering hypothesis testing, non-parametric methods, and exploratory data visualization.

---

## Tech Stack

- **R** — core language
- **R Markdown** — reproducible report format (HTML output)
- **tidyverse** — data manipulation and piping
- **ggplot2** — visualizations
- **ggpubr** — publication-ready plots
- **dplyr** — data wrangling

---

## Assignment 1 — Drug Effect Analysis

**Dataset:** Clinical study — 20 patients scored at 3 time points (initial exam, 60-day control, 90-day control), with sex recorded.

**Analysis:**

1. **Normality testing** — Shapiro-Wilk test applied to all three time points (overall and by sex). All groups found non-normal (p < 0.05).
2. **Score change over time** — Paired Wilcoxon signed-rank test. Statistically significant improvement found between initial and 60-day (p < 0.05) and initial and 90-day scores (p < 0.05) → drug has a significant effect.
3. **Sex differences** — Independent Wilcoxon test at each time point. No statistically significant difference between males and females (p > 0.05 at all points).

**Visualizations:**
- Boxplot of score change over time (with jitter overlay)
- Faceted boxplot comparing scores by sex across time points
- Line chart of mean score over time

---

## Assignment 2 — World Happiness Report 2019

**Dataset:** `2019.csv` — World Happiness Report with happiness score and contributing factors (GDP, social support, life expectancy, freedom, generosity, corruption perception) for 156 countries.

**Analysis:**

1. **Top 10 happiest countries** — horizontal bar chart. Northern/Central European countries dominate.
2. **Happiness vs GDP** — scatter plot with linear regression line. Strong positive correlation observed.
3. **Regional comparison** — countries manually grouped into 14 regions. Boxplot of happiness by region. Northern Europe highest, South Asia and Sub-Saharan Africa lowest, Balkans in the middle.
4. **Finland vs Syria** — detailed comparison across all 6 indicators. Finland higher on all measures except generosity. GDP, social support, and healthy life expectancy identified as the strongest predictors of happiness.

---

## How to Run

```r
# Install required packages
install.packages(c("tidyverse", "ggplot2", "ggpubr", "readr", "dplyr"))

# Open in RStudio and knit to HTML
rmarkdown::render("drug.Rmd")
rmarkdown::render("happiness.Rmd")
```

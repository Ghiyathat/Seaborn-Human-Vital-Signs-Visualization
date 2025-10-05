## Human Vital Signs Visualization with Seaborn
This project explores the distribution, relationships and correlations among human vital signs using Seaborn, a python visualization library. It demonstrates how visual analytics can help identify patterns in patient demographics and clinical indicators that support clinical decision-making.

### Dataset Overview

The dataset contains physiological measurements and derived indicators for patients such as;
- Heart Rate (bpm)
- Respiratory Rate (breaths/min)
- Body Temperature (°C)
- Oxygen Saturation (%)
- Systolic Blood Pressure (mmHg)
- Diastolic Blood Pressure (mmHg)
- Age (years)
- Gender
- Weight (kg)
- Height (m)
- Derived HRV (Heart Rate Variability)
- Derived Pulse Pressure
- Derived BMI
- Derived MAP (Mean Arterial Pressure)
- Risk Category (High/Low)

### Methodological Analysis
This project uses Seaborn to visualize and interpret health data distributions, demographic patterns, and inter-variable relationships. A sample is shown below;

```python
# Importing Libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Reading dataset
vitalsigns_df = pd.read_csv('./human_vital_signs_dataset_2024_2000_data.csv')
vitalsigns_df
```

### Age Distribution — Histogram Plot

```python
sns.histplot(data= vitalsigns_df, x= "Age", bins= 20, kde= True, color= "green")
plt.title("Distribution of Patient Age")
plt.xlabel("Age (years)")
plt.ylabel("Count")
plt.show()
```
Explanation:

- The histogram displays the frequency of patients within age ranges, from about 20 to 90 years.
- X-axis: Age bins (5-year intervals).
- Y-axis: Count of patients.
- The distribution is irregular and multimodal, with notable peaks around 30–35, 55–60, 65–70, and 80–85 years.
- Low frequencies appear in early 20s, mid-40s, and early 70s.
- The histogram reveals age clusters and potential risk concentration zones, identifying whether the sample leans toward younger or older patients

### Heart Rate by Gender — Box Plot

Explanation:

- The boxplot compares heart rate distributions across gender.
- Median heart rate: ~79 bpm for both male and female, showing similar central tendency.

IQR:

- Males: ~70–89 bpm
- Females: ~69–89 bpm
- Whiskers: Extend from ~60 bpm (lower end) to ~99 bpm (upper end), indicating similar overall range.
- No visible outliers detected.

The visualization shows similar cardiac profiles across gender, with overlapping spreads and nearly identical medians — suggesting uniform cardiovascular behavior across demographics.

### Body Temperature by Risk Category — Violin Plot

Explanation:
- The violin plot illustrates the distribution of body temperature for High and Low risk categories.
- Both clusters around 36.5–37°C, but:
  - High risk (red) group is wider, showing higher variability and a secondary peak near 36.35°C.
  - Low risk (blue) group is narrower, concentrated near 36.7°C, indicating more stability.
- Median: ~36.7°C for both.

IQR: Wider for high-risk, narrower for low-risk patients.

This visualization combines boxplot structure with kernel density, showing that high-risk patients exhibit greater variability in body temperature, possibly reflecting underlying health instability.

### Correlation Heatmap — Clinical Variable Relationships

Explanation:

The heatmap visualizes pairwise correlations between all clinical indicators.

Color scale:

- Deep red = strong positive correlation
- Dark blue = strong negative correlation
- Light colors = weak or no correlation
- Diagonal values (1.0) indicate perfect self-correlation.

Example: Heart Rate vs Respiratory Rate → correlation ≈ -0.01, showing a weak negative relationship.

Enables quick identification of which physiological variables move together, helping to reveal dependencies useful for clinical risk modeling.

### Key Insights
- Patient age distribution is non-uniform, with clusters around mid-adulthood and senior years.
- Heart rate distributions are similar across gender, indicating minimal demographic variation.
- High-risk patients exhibit greater variability in body temperature — potential sign of instability.
- Correlation analysis highlights weak to moderate relationships, supporting multidimensional interpretation of vital signs.

### Key Concepts Demonstrated

- Seaborn data visualization (histplot, boxplot, violinplot, heatmap)
- Exploratory Data Analysis (EDA) in healthcare datasets
- Correlation and statistical pattern detection
- Visual storytelling in clinical data interpretation

### Tools
- Python
- Seaborn
- Matplotlib
- Pandas
- NumPy

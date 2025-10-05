## Human Vital Signs Visualization with Seaborn
This project explores the distribution, relationships and correlations among human vital signs using Seaborn, a python visualization library. It demonstrates how visual analytics can help identify patterns in patient demographics and clinical indicators that support clinical decision-making.

### Dataset Overview








### Methodological Analysis






### Explanation








### Conclusion
### Recommendation




```python
# Importing Libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns


# Reading dataset
vitalsigns_df = pd.read_csv('./human_vital_signs_dataset_2024_2000_data.csv')
vitalsigns_df

# Distribution of patients age

sns.histplot(data= vitalsigns_df, x= "Age", bins= 20, kde= True, color= "green")
plt.title("Distribution of Patient Age")
plt.xlabel("Age (years)")
plt.ylabel("Count")
plt.show() 




















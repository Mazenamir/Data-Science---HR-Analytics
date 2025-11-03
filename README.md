# HR Employee Attrition Analysis Notebook

## Overview
This Jupyter notebook (`HR_Proj.ipynb`) performs exploratory data analysis (EDA) on an HR employee dataset to understand factors related to employee attrition. It uses Python libraries to load, inspect, and visualize the data, focusing on attrition rates, demographics like gender, and other key metrics. The dataset includes information on employees such as age, department, education, job satisfaction, and more.

The analysis helps identify patterns in employee turnover, which can inform HR strategies for retention.

## Features
- **Data Loading and Inspection**: Loads the CSV data into a Pandas DataFrame and provides summaries (head, info, describe).
- **Data Quality Checks**: Verifies for null values, duplicates, and unique values in categorical columns.
- **Visualizations**:
  - Bar plot for overall attrition counts.
  - Pie charts for attrition distribution by gender (separate for males and females).
  - Additional plots (e.g., bar plots for female attrition) – note: some cells may contain errors that need debugging.
- **Error Handling Insight**: The notebook includes an example of a common plotting error for educational purposes, demonstrating issues with mismatched data lengths in Seaborn.

## Requirements
- Python 3.x (tested with 3.13.0)
- Libraries:
  - pandas
  - numpy
  - seaborn
  - matplotlib
  - warnings (built-in)

Install dependencies using:
```
pip install pandas numpy seaborn matplotlib
```

- Jupyter Notebook or JupyterLab for running the `.ipynb` file.

## Data Files
The notebook expects the following CSV file in the same directory:
- `HR-Employee-Attrition.csv`

This file contains 1470 rows and 35 columns, including:
- Numerical features: Age, DailyRate, DistanceFromHome, etc.
- Categorical features: Attrition (Yes/No), BusinessTravel, Department, EducationField, Gender, JobRole, MaritalStatus, etc.

No missing values are present in the dataset.

## Usage
1. Place the `HR-Employee-Attrition.csv` file in the same folder as the notebook.
2. Open the notebook in Jupyter:
   ```
   jupyter notebook HR_Proj.ipynb
   ```
   or
   ```
   jupyter lab HR_Proj.ipynb
   ```
3. Run the cells sequentially:
   - Import libraries.
   - Load and explore the data (head, info, describe).
   - Check for duplicates and unique values.
   - Generate visualizations for attrition analysis.
4. Debug any errors (e.g., the last barplot cell has a mismatch in data lengths – fix by computing counts on `female_df` instead of the full `df`).

Example fix for the error in the last cell:
```python
attrition_counts = female_df['Attrition'].value_counts()
sns.barplot(y=attrition_counts.index, x=attrition_counts.values)
```

## Code Structure
- **Cell 1**: Markdown - Importing Libraries.
- **Cell 2**: Code - Import pandas, numpy, seaborn, matplotlib, warnings.
- **Cell 3**: Markdown - Explore the data.
- **Cell 4**: Code - Load CSV into `df` and display `df.head()`.
- **Cell 5**: Code - `df.info()` (shows data types and non-null counts).
- **Cell 6**: Code - `df.describe()` (summary statistics).
- **Cell 7**: Code - Check for duplicates (`df.duplicated().sum()`).
- **Cell 8**: Code - Unique values in categorical columns.
- **Cell 9**: Code - Bar plot for attrition counts.
- **Cell 10**: Code - Pie charts for attrition by gender (males and females).
- **Cell 11**: Code - Attempted bar plot for female attrition (contains error for debugging/learning).

## Limitations
- The dataset is static and limited to 1470 entries; no real-time data integration.
- Some visualizations (e.g., the final bar plot) contain errors due to mismatched data frames – intended for educational purposes or requires manual fixes.
- No advanced modeling (e.g., machine learning for prediction); focused solely on EDA.
- Assumes the CSV file is present; no error handling for missing files.

## Contributing
Feel free to fork this repository and submit pull requests for enhancements, such as adding more visualizations, predictive modeling, or fixing existing errors.

## License
This project is open-source and available under the MIT License.

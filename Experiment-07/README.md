# Experiment 7: Data Cleaning and Exploratory Data Analysis Using Pandas

## Aim
To perform data cleaning, missing value treatment, aggregation, and exploratory data analysis on a sample real-world-style student dataset using Pandas.

## Algorithm
1. Start the program.
2. Create or load a CSV dataset using Pandas.
3. Inspect the dataset using head(), info(), and isnull().sum().
4. Identify missing values.
5. Fill missing numeric values with the column mean and missing categorical values with the mode.
6. Remove duplicate records if present.
7. Perform aggregation such as department-wise average marks.
8. Perform exploratory analysis using descriptive statistics.
9. Display the cleaned dataset and analysis results.
10. Stop the program.

## Program
See [data_cleaning_eda.py](data_cleaning_eda.py) (In-memory DataFrame) and [data_cleaning_csv.py](data_cleaning_csv.py) (CSV-based)

```python
# Data Cleaning and Exploratory Data Analysis using Pandas
import pandas as pd

data = {
    "Name": ["Anitha", "Bala", "Chitra", "Dinesh", "Ezhil", "Fathima"],
    "Department": ["CSE", "CSE", "ECE", "CSE", "ECE", "CSE"],
    "Attendance": [92, 85, None, 88, 95, 90],
    "Mark": [86, 91, 78, None, 95, 82]
}

df = pd.DataFrame(data)
print("--- Original Dataset ---")
print(df)

print("\nMissing Values:")
print(df.isnull().sum())

# Missing value treatment
df["Attendance"] = df["Attendance"].fillna(df["Attendance"].mean())
df["Mark"] = df["Mark"].fillna(df["Mark"].mean())

# Remove duplicate records
df = df.drop_duplicates()
print("\n--- Cleaned Dataset ---")
print(df)

print("\n--- Descriptive Statistics ---")
print(df.describe())

print("\n--- Department-wise Average Marks ---")
print(df.groupby("Department")["Mark"].mean().round(2))

print("\n--- EDA Summary ---")
print("Highest Mark :", df["Mark"].max())
print("Lowest Mark :", df["Mark"].min())
print("Average Mark :", round(df["Mark"].mean(), 2))
print("Average Attendance :", round(df["Attendance"].mean(), 2))
```

## Output
See [output.txt](output.txt)

```
--- Original Dataset ---
      Name Department  Attendance  Mark
0   Anitha        CSE        92.0  86.0
1     Bala        CSE        85.0  91.0
2   Chitra        ECE         NaN  78.0
3   Dinesh        CSE        88.0   NaN
4    Ezhil        ECE        95.0  95.0
5  Fathima        CSE        90.0  82.0

Missing Values:
Name          0
Department    0
Attendance    1
Mark          1
dtype: int64

--- Cleaned Dataset ---
      Name Department  Attendance  Mark
0   Anitha        CSE        92.0  86.0
1     Bala        CSE        85.0  91.0
2   Chitra        ECE        90.0  78.0
3   Dinesh        CSE        88.0  86.4
4    Ezhil        ECE        95.0  95.0
5  Fathima        CSE        90.0  82.0

--- Descriptive Statistics ---
       Attendance       Mark
count    6.000000   6.000000
mean    90.000000  86.400000
std      3.577709   6.349803
min     85.000000  78.000000
25%     88.500000  83.000000
50%     90.000000  86.200000
75%     91.500000  89.750000
max     95.000000  95.000000

--- Department-wise Average Marks ---
Department
CSE    86.35
ECE    86.50
Name: Mark, dtype: float64

--- EDA Summary ---
Highest Mark : 95.0
Lowest Mark : 78.0
Average Mark : 86.4
Average Attendance : 90.0
```

## Result
Thus, data cleaning, missing value treatment, aggregation, descriptive analysis, and basic exploratory data analysis were performed successfully using Pandas.

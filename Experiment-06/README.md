# Experiment 6: Analysis of Student Dataset Using Pandas Series and Data Frames

## Aim
To create and manipulate Pandas Series and DataFrames for analyzing a student dataset.

## Algorithm
1. Start the program.
2. Import the Pandas library.
3. Create a Pandas Series containing marks.
4. Create a DataFrame containing student details and marks.
5. Calculate total or average marks and identify high-performing students.
6. Display the Series and DataFrame results.
7. Stop the program.

## Program
See [student_dataset_pandas.py](student_dataset_pandas.py)

```python
# Pandas Series and DataFrame
import pandas as pd

marks = pd.Series([85, 91, 78, 88, 95],
                  index=["A", "B", "C", "D", "E"])
print("--- Pandas Series ---")
print(marks)

data = {
    "RollNo": [101, 102, 103, 104, 105],
    "Name": ["Anitha", "Bala", "Chitra", "Dinesh", "Ezhil"],
    "Department": ["CSE", "CSE", "ECE", "CSE", "ECE"],
    "Mark": [85, 91, 78, 88, 95]
}

df = pd.DataFrame(data)
print("\n--- DataFrame ---")
print(df)

print("\nAverage Mark:", round(df["Mark"].mean(), 2))

print("\nStudents scoring above 85:")
print(df[df["Mark"] > 85])
```

## Output
See [output.txt](output.txt)

```
--- Pandas Series ---
A    85
B    91
C    78
D    88
E    95
dtype: int64

--- DataFrame ---
   RollNo    Name Department  Mark
0     101  Anitha        CSE    85
1     102    Bala        CSE    91
2     103  Chitra        ECE    78
3     104  Dinesh        CSE    88
4     105   Ezhil        ECE    95

Average Mark: 87.4

Students scoring above 85:
   RollNo    Name Department  Mark
1     102    Bala        CSE    91
3     104  Dinesh        CSE    88
4     105   Ezhil        ECE    95
```

## Result
Thus, Pandas Series and DataFrame were created and manipulated successfully for student dataset analysis.

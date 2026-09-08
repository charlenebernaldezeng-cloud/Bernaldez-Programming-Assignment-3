# Bernaldez-Programming-Assignment-3
This repository contains my solutions for Experiment 3: Python Data Analysis (Pandas)

The programming assignment contains three Experiment Problems:

A.) Positional and label-based slicing
- In this problem, the code imports Pandas and reads the given cars.csv file into a DataFrame called cars. It checks the data's shape to show the number of rows and columns and displays the column names. Afterward, cars.iloc[5:10] selects rows 6 to 10 by position. Lastly, the code displays only the selected columns: Model, mpg, cycl, hp, and gear.
  
B.) Model Lookup
- This problem demonstrates Boolean indexing. First, it selects the complete row of the Toyota Corolla by checking which row model is equal to "Toyota Corolla". Then, it uses .iloc[] to find the Pontiac Firebird and display only its Model, mpg, hp, and wt columns.

C.) Multi-Model Subsetting
- For this last problem, the code demonstrates multi-model subsetting. It uses .isin() to filter the cars DataFrame and select only the specified rows. It then selects only the columns Model, mpg, cyl, hp, and gear. Finally, it displays the selected cars, which uses .shape to show the number of rows and columns in the filtered DataFrame.

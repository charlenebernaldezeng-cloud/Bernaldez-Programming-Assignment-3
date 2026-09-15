# ECE 2112 - Programming Assignment 3
### Name: Bernaldez, Charlene A.                                                                           
### Section: 2ECE-B

## Table of Contents
- [Overview](#overview)
- [Task Summary](#task-summary)
- [Problems & Solutions](#problems--solutions)
  - [A. Positional and Label-Based Slicing](#a-positional-and-label-based-slicing)
  - [B. Model Lookup](#b-model-lookup)
  - [C. Multi-Model Subsetting](#c-multi-model-subsetting)
- [Project File Structure](#project-file-structure)
- [How to Run](#how-to-run)

---

## Overview

This repository features Python-based solutions for Experiment 3: Python Data Analysis (Pandas). The exercises involve loading a CSV dataset into a Pandas DataFrame and extracting well-defined subsets of data without changing the source data. It highlights programming concepts such as:
* Loading a CSV dataset into a Pandas DataFrame.
* Selecting rows and columns using positional and label-based indexing.
* Filtering records using Boolean conditions on a DataFrame column.

---

## Task Summary

| Task | Key DataFrame Operations | Expected Output |
| :--- | :--- | :--- |
| **A. Slicing** | `.shape`, `.columns`, `.iloc[]`, label-based indexing | DataFrame shape, column list, and rows 6-10 with specific columns[cite: 1] |
| **B. Model Lookup** | Boolean indexing on a column | Full row for "Toyota Corolla" and a subset of columns for "Pontiac Firebird"[cite: 1] |
| **C. Multi-Model Subsetting** | `.isin()` for filtering multiple values | A 3-row by 5-column DataFrame of specific models[cite: 1] |

---

## Problems & Solutions

### A. Positional and Label-Based Slicing
* *Description:* Loads the dataset, displays the shape and column names, extracts rows 6 through 10 using positional slicing (`iloc`), and then displays specific columns (`Model`, `mpg`, `cyl`, `hp`, `gear`) using label-based indexing[cite: 1].

code:

      # Display shape of cars
      print('Shape of cars: ')
      cars = pd.read_csv('cars.csv')
      print (cars.shape)

      # Display the list of column names of cars
      print('\nColumn names of cars:')
      print(cars.columns.tolist()) 

      # Display rows 6 to 10
      cars_6_to_10 = cars.iloc[5:10] 
      print('\ncars rows 6 to 10:')
      print(cars_6_to_10)

      print('\nselected rows 6 to 10:')
      print(cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']])

### B. Model Lookup
* *Description:* Uses Boolean indexing on the Model column to locate specific vehicles and extract their data into separate variables without using hard-coded row numbers.

code:

      # Display complete row for Toyota Corolla
      print('Toyota Corolla: ' )
      toyota = cars[cars['Model'] == 'Toyota Corolla'] 
      print (toyota)

      # Display Model, mpg, hp, and wt of Pontiac Firebird
      pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']] 

      print('\nPontiac Firebird:')
      print(pontiac)

### C. Multi-Model Subsetting
* *Description:* Creates a new DataFrame containing only the records for Datsun 710, Lotus Europa, and Ferrari Dino. Retains only the columns Model, mpg, cyl, hp, and gear, and verifies the shape of the resulting subset.

code:

      # Select rows for the three specified car models 
      selected_cars = cars[cars['Model'].isin(['Datsun 710', 'Lotus Europa', 'Ferrari Dino'])][['Model', 'mpg', 'cyl', 'hp', 'gear']]

      # Display the selected cars
      print(selected_cars) 

      # Display the shape of the DataFrame
      print('\nShape of selected_cars:') 
      print(selected_cars.shape)

## Project File Structure
```text
Bernaldez---Programming-Assignment-3/
│
├── ECE2112_PA3.ipynb       # Main Jupyter Notebook containing Pandas solutions
└── cars.csv                # Source dataset for the experiment
└── README.md               # Project documentation
```
## How to Run
### Using Terminal / Command Prompt
1. Clone or download the repository to your local machine.
2. Ensure that your `cars.csv` dataset is saved in the exact same directory as your notebook.
3. Open your terminal or command prompt and navigate to the project directory:
   ```bash
   git clone [https://github.com/charlenebernaldezeng-cloud/Bernaldez-Programming-Assignment-3.git](https://github.com/charlenebernaldezeng-cloud/Bernaldez-Programming-Assignment-3.git)
   cd Bernaldez-Programming-Assignment-3

4. Launch Jupyter Notebook:
   ```bash
   jupyter notebook

5. Open `ECE2112_PA3.ipynb` from the browser interface and run all cells sequentially (`Cell > Run All`).

### Using Jupyter Notebook / VS Code
1. Open the project folder in your preferred IDE (e.g., Visual Studio Code).
2. Ensure that your cars.csv dataset is saved in the same project folder.
3. Open `ECE2112_PA3.ipynb`.
4. Ensure your Python environment has the pandas library installed.
5. Execute the cells from top to bottom.
6. Ensure that your `cars.csv` dataset is saved in the exact same directory as your notebook.
   




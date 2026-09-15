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

  ```python
  import pandas as pd

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
  
 ```B. Model Lookup  Description: Uses Boolean indexing on the Model column to locate specific vehicles and extract their data into separate variables without using hard-coded row numbers[cite: 1].
  

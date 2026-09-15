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
* Loading a CSV dataset into a Pandas DataFrame[cite: 1].
* Selecting rows and columns using positional and label-based indexing[cite: 1].
* Filtering records using Boolean conditions on a DataFrame column[cite: 1].

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

  # Load the CSV file into a DataFrame named cars[cite: 1]
  cars = pd.read_csv('cars.csv')

  # a. Display the shape and complete list of column names[cite: 1]
  print("Shape of cars:", cars.shape)
  print("\nColumns in cars:", cars.columns.tolist())

  # b. Create cars_6_to_10 containing rows 6 through 10 using iloc[cite: 1]
  # Since the first data row is row 1 (index 0), rows 6 through 10 correspond to indices 5 to 9[cite: 1]
  cars_6_to_10 = cars.iloc

  # c. Display only the columns Model, mpg, cyl, hp, and gear[cite: 1]
  subset_A = cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]
  print("\nRows 6 to 10 with specified columns:\n", subset_A)

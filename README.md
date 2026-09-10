# ECE-2112 - Programming Assignment 3
**By: Macni, Julian Diether J. | 2ECE-B**
### Overview
This repository contains the Programming Assignment 3 for ECE 2112 - Advanced Computer Programming and Algorithms. The problems for this assignment covers Module 3, which covers concepts related to the Pandas library, such as how to make and edit tabular data, as well as how to perform indexing, slicing, and subsetting, on these data.

Before proceeding with the different problems, the following code should be created in order for the program to function correctly:

• `import pandas as pd` - gives access to the Pandas Library for creating and editing data structures.

• `pd.read_csv()` - imports the given CSV file, in which for this assignment, the `cars.csv` file is used to load the table.

## A. Positional and Label-Based Slicing
**Objective:** Display the given CSV file, its shape and column names, as well as only display specific rows and columns, which is rows 6 to 10 and the columns: Model, mpg, cyl, hp, and gear.

The following functions or methods were used in this problem:

• `.shape` - displays the shape of the dataframe, in which it returns the number of rows and columns.

Example: `cars.shape` results to `(32, 12)`, which means there are 32 rows and 12 columns.

• `.columns` - displays the different column names of the dataframe.

Example: `cars.columns` results in
```python
Index(['Model', 'mpg', 'cyl', 'disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am',
       'gear', 'carb'],
      dtype='str')
```

• `.iloc[x, y]` - used to only display the specific rows (x) and columns (y) based on their index positions. A colon `:` can be used to select all rows/columns, or to specify a specific range.

Example: `cars.iloc[6:11]` will only display rows 6 to 10, and all the columns

• `.loc[[M],[N]]` - similar to the `.iloc[x, y]`, but can select rows and columns using label names or even Boolean conditions instead of numerical values.

Example: `cars_6_to_10.loc[6:11, ['Model', 'mpg', 'cyl', 'hp', 'gear']]` will only display rows 6 to 10, and only the columns: Model, mpg, cyl, hp, and gear.

These methods were combined in order to display the shape, column names, as well as specific rows and columns in the given table:
```python
cars.shape
cars.columns
cars_6_to_10 = cars.iloc[6:11]
cars_6_to_10.loc[:, ['Model', 'mpg', 'cyl', 'hp', 'gear']]
```




## B. Model Lookup
**Objective:** Display the complete row of **Toyota Corolla**, and the row **Pontiac Firebird** with only the columns: Model, mpg, hp, and wt.

The following functions or methods were used in this problem:

• `.loc[[M],[N]]` - selects rows and columns using label names or even Boolean conditions instead of just numerical values.

• **Boolean Indexing** - used to only display rows or columns that satisfy certain conditions.

Example: `cars.loc[cars['Model'] == 'Toyota Corolla']` which will only display the complete row of Toyota Corolla.

These methods were combined in order to display the complete row of Toyota Corolla as well as Pontiac Firebird with specific columns:
```python
toyota = cars.loc[cars['Model'] == 'Toyota Corolla']
pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]
```




## C. Multi-Model Subsetting
**Objective:** Create a dataframe only containing the models **Datsun 710**, **Lotus Europa**, and **Ferrari Dino**, as well as only display the columns: Model, mpg, cyl, hp, and gear. After that, display the shape of the completed table.

The following functions or methods were used in this problem:

• `.loc[[M],[N]]` - selects rows and columns using label names or even Boolean conditions instead of just numerical values.

• **Boolean Indexing** - used to only display rows or columns that satisfy certain conditions. Multiple conditions can be combined using operators like `|` (OR).

• `.shape` - displays the shape of the dataframe, in which it returns the number of rows and columns.

These methods were combined to only display the specified models and columns, as well as the shape of the completed dataframe:
```python
selected_cars = cars.loc[(cars['Model'] == 'Datsun 710') |
                        (cars['Model'] == 'Lotus Europa') |
                        (cars['Model'] == 'Ferrari Dino'),
                        ['Model', 'mpg', 'cyl', 'hp', 'gear']]
selected_cars.shape
```

Thank you for reading!

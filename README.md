## <center> __University of Santo Tomas – Faculty of Engineering Electronics Engineering Department__ </center>
## <center> __ECE 2112: Advanced Computer Programming and Algorithms__ </center>
# <center> __EXPERIMENT 1: INTRODUCTION TO PYTHON PROGRAMMING__ </center> 
#### Emmanuelle D.G. Miran| 2ECE-C
## **I.** Intended Learning Outcomes
1. Load a CSV dataset into a Pandas DataFrame;
2. Select rows and columns using positional and label-based indexing;
3. Filter records using conditions on a DataFrame column; and
4. Extract a well-defined subset of data without changing the source data.
## **II.** Numpy Initialization
```python
import pandas as pd
cars = pd.read_csv("cars.csv")
cars
```
## **III.** Programming Problems
>  ##  **A.** POSITIONAL AND LABEL-BASED SLICING
>After loading **cars**, complete the following operations.<br>
>>**A.** Display the shape and complete list of column names of cars.<br>
>>**B.** Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where the first data row is row 1.<br>
>>**C.** From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.<br>
>**Requirement:** The row selection in part (b) must use iloc; the column selection in part (c) must use column labels.
> ## Explanation

>>For this programming problem, the first thing we need to do is to initialize the **cars.csv** file into the Panda's dataframe. To do this, we need to use the function ***pd.read_csv()***. This function was accomplished in the previous section of the **PA**.<br><br>
>>To be able to display the shape and complete list of column names of cars, we are to use two different functions. The first function is ***.shape***, which simply returns the dimensions of the dataset given in the **.csv** file. The second function that we will use is ***.columns***, this function allows us to display all of the names of each column from the **.csv** file.<br><br>
>>To create a set of rows from 6 through 10 of the data set, we will use the function ***.iloc[]***. This function allows us to select specific rows and columns from the Data Frame designated by their numerical position. For this specific problem we will be using the function ***cars.iloc[5:10]*** This is because, from what I understand, we were asked to get rows 6 to 10 from the data frame, which would be the equivalent of 5 to 10 in Python because it uses zero-based indexing. We start with 5 in the function because that is the equivalent of 6 from the data frame, and we end at 10 because it tells the function to stop right before that row.<br><br>
>>To tackle the last part, we will use the function ***cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]***. This allows us to display only these specific columns in the specific order that we listed them in. This was only possible to be executed because we defined what **cars_6_to_10** is at the previous requirement.

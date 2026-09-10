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
> ## Code & Outputs
```python
Shape=cars.shape
Shape
```
```(32, 12)```
```python
Columns_of_Names = cars.columns
Columns_of_Names
```
```
Index(['Model', 'mpg', 'cyl', 'disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am',
       'gear', 'carb'],
      dtype='str')
```
```python
cars_6_to_10 = cars.iloc[5:10]
cars_6_to_10
```
```
         Model   mpg  cyl   disp   hp  drat    wt   qsec  vs  am  gear  carb
5     Valiant  18.1    6  225.0  105  2.76  3.46  20.22   1   0     3     1
6  Duster 360  14.3    8  360.0  245  3.21  3.57  15.84   0   0     3     4
7   Merc 240D  24.4    4  146.7   62  3.69  3.19  20.00   1   0     4     2
8    Merc 230  22.8    4  140.8   95  3.92  3.15  22.90   1   0     4     2
```
```python
cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]
```
```
         Model   mpg  cyl   hp  gear
5     Valiant  18.1    6  105     3
6  Duster 360  14.3    8  245     3
7   Merc 240D  24.4    4   62     4
8    Merc 230  22.8    4   95     4
```
>  ##  **B.** MODEL LOOKUP
>Use Boolean indexing on the Model column to answer both requests<br>
>>**A.** Display the complete row for Toyota Corolla.<br>
>>**B.** For Pontiac Firebird, display only Model, mpg, hp, and wt.<br>
>Store the two results in toyota and pontiac, respectively. Do not use a hard-coded row number to locate either model.
> ## Explanation

>>For this programming problem, we were tasked to display the complete row for the Toyota Corolla. To accomplish this we use something called **Boolean Slicing** with the function ***cars[cars['Model'] == 'Toyota Corolla']***. To explain this function, we will break it down into parts. In this function **cars['Model'] == 'Toyota Corolla'** basically checks the **Model** column if any of the individual rows include the word **Toyota Corolla** and it labels this as true and anything else as false. The outer **cars[]** will allow us to display all the rows that were labeled as **True**.<br><br>
>>For the next required problem, it is basically the same as the **Toyota Corolla** problem, but we identify the **Pontiac Firebird** instead, with an added condition where it will only display the columns **Model**, **mpg**, **hp**, and **wt**. This can be done in the same way as the final condition at the previous programming problem; we use the function ***[['Model', 'mpg', 'hp', 'wt']]***.
>>
> ## Code & Outputs
```python
toyota = cars[cars['Model'] == 'Toyota Corolla']
toyota
```
```
              Model   mpg  cyl  disp  hp  drat     wt  qsec  vs  am  gear  carb
19  Toyota Corolla  33.9    4  71.1  65  4.22  1.835  19.9   1   1     4     1
```
```python
pontiac = cars[cars['Model'] == 'Pontiac Firebird'] [['Model', 'mpg', 'hp', 'wt']]
pontiac
```
```
                Model   mpg   hp     wt
24  Pontiac Firebird  19.2  175  3.845
```
>  ##  **C.** Multi-Model Subsetting
>Create a DataFrame named selected cars containing only the records for three models: Datsun 710, Lotus Europa, and Ferrari Dino.<br>
>For these records, retain only Model, mpg, cyl, hp, and gear. Select the rows by their model values rather than by row numbers. Display selected cars and its shape. <br>
>**Required check:** The final DataFrame must contain exactly three rows and five columns
> ## Explanation

>>For this programming problem, we were tasked to create a DataFrame named **selected cars** containing three models: Datsun 710, Lotus Europa, and Ferrari Dino. To solve this, we essentially need to redo what we did for the previous programming problem, where we used the function ***cars['Model'] == ' '*** to check if a specific model of a car is in the **Model** column. The only difference here now is that we check for three different models at the same time rather than just one. To accomplish this, we can either simply use the symbol **|** to represent **OR** in the function by, or we can add the function .isin() so we don't have to redo the ***cars['Model'] == ' '*** three times. For this programming problem I will be using **.isin()**.<br><br>
>>To retain only the **Model**, **mpg**, **cyl**, **hp**, and **gear**. We will use the function ***[["Model", "mpg", "cyl", "hp", "gear"]]*** which is similar to the function we used on both the final conditions of the last two programming problems.<br><br>
>>To do the required check we can simply use the function ***.shape***.
> ## Code & Outputs
```python
selected_cars = cars[cars['Model'].isin(['Datsun 710', 'Lotus Europa', 'Ferrari Dino'])] [["Model", "mpg", "cyl", "hp", "gear"]]
selected_cars 
```
```
            Model   mpg  cyl   hp  gear
2     Datsun 710  22.8    4   93     4
27  Lotus Europa  30.4    4  113     5
29  Ferrari Dino  19.7    6  175     5
```
```python
selected_cars.shape
```
```
(3, 5)
```
README File Version History:

```September 10, 2026 ```- Initial README.md was uploaded
```September 11, 2026``` - Fixed wrong header and titles. Formatting changes.

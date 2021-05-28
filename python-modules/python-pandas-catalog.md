
# PANDAS <!-- omit in toc -->


This is a guide for the Python Module **Pandas**´s commands.
<!-- --><br/>

> **Notes:**
>
>> You can start at [SERIES](#series).

<!-- --><br/>

------------------------------------

### TABLE OF CONTENT <!-- omit in toc -->


- [TERMINOLOGY](#terminology)
- [PACKAGES](#packages)
- [REFERENCES](#references)
- [SERIES](#series)
- [DATAFRAMES](#dataframes)
    - [Creating and Adding data](#creating-and-adding-data)
    - [Indexing & Slicing](#indexing--slicing)
    - [Removing Lines and Columns](#removing-lines-and-columns)
- [METHODS & PARAMETERS](#methods--parameters)
    - [Methods for Info](#methods-for-info)
    - [Methods to modify Index](#methods-to-modify-index)
    - [Methods for Operations over Index and Columns](#methods-for-operations-over-index-and-columns)
    - [Methods for Operations over Values](#methods-for-operations-over-values)
    - [Map and Apply](#map-and-apply)
    - [Misc Methods](#misc-methods)
    - [Parameters](#parameters)
- [BOOLEAN OPERATIONS & FILTERS](#boolean-operations--filters)
    - [Filter](#filter)
    - [Multiple Filters](#multiple-filters)
- [MULTIINDEX (HIERARCHICAL INDEX) & NAMES](#multiindex-hierarchical-index--names)
    - [Hierarchical Index](#hierarchical-index)
    - [Name](#name)
    - [Cross-Sections](#cross-sections)
- [PIVOT TABLE](#pivot-table)
- [MISSING DATA](#missing-data)
- [GROUP BY](#group-by)
    - [Methods](#methods)
    - [Unstack](#unstack)
- [CONCATENATE, MERGE & JOIN](#concatenate-merge--join)
    - [Concatenate](#concatenate)
    - [Merge](#merge)
    - [Join](#join)
- [INPUT & OUTPUT DATA](#input--output-data)
    - [File '.csv'](#file-csv)
    - [File '.xlsx'](#file-xlsx)
    - [File '.html'](#file-html)
    - [Cool Image](#cool-image)
- [DATA VISUALIZATION](#data-visualization)
    - [Simple Plot](#simple-plot)
    - [Histogram](#histogram)
    - [Lines](#lines)
    - [Stacked Area Plot](#stacked-area-plot)
    - [Bars](#bars)
    - [Scatter](#scatter)
    - [Box Plot](#box-plot)
    - [Hexagon Plot](#hexagon-plot)
    - [Kernel Density Estimation](#kernel-density-estimation)
- [DATAREADER](#datareader)

<!-- --><br/>


- [Generate a Table of Content from a Markdown file](https://ecotrust-canada.github.io/markdown-toc/ "Table of contents generated with markdown-toc")
<!-- --><br/>



------------------------------------

### TERMINOLOGY


| Term/Expression | Meaning |
| --------------: | :------ |
| `<description>` | To replace, or that will be replaced, according to description. |
| `...`           | Possible to repeated pattern. |
| `$`             | Some command to be used on the Terminal (shell). |
| `>>>`           | Some IPython (Interactive Python) command. |
<!-- --><br/>
<!-- --><br/>



- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### PACKAGES


| Source | Package | Description |
| :----: | ------- | ----------- |
| pacman | python-pandas | High-performance, easy-to-use data structures and data analysis tools for Python. |
| conda  | pandas | - |
| conda  | pandas-datareader | Up to date remote data access for pandas, works for multiple versions of pandas. |
| pacman | python-pandas-datareader | Data readers extracted from the pandas codebase. |
| conda-forge  | dataframe_image | - |
<!-- --><br/>


**Info**

- Open Library written over Numpy.
- Data Visualization tool.
- Similar to Excel.

**Imports**

Imports used on most commands and examples:

```python
import numpy as np
```
```python
import pandas as pd
```
```python
import pandas-datareader as pdr
```
<!-- --><br/>
<!-- --><br/>



- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



----------------------------------

### REFERENCES

- [Pandas Home Page][home]


- [Pandas Documentation][doc]


- [Numpy Universal Functions][np-func]


- [Pandas DataReader Documentation][datareader]


- [Remote Data Access][remote-data]
<!-- --><br/>
<!-- --><br/>



- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



[home]:https://pandas.pydata.org "Pandas Home Page"
[doc]:https://pandas.pydata.org/pandas-docs/stable/index.html "Pandas Documentation"

[np-func]:https://numpy.org/doc/stable/reference/ufuncs.html
[datareader]:https://pandas-datareader.readthedocs.io/en/stable/
[remote-data]:https://pandas-datareader.readthedocs.io/en/stable/remote_data.html

[pct_change]:./../imgs/modules/pandas_pct_change.png
[lines]:./../imgs/modules/pandas_lines.png
[stacked_area]:./../imgs/modules/pandas_stacked_area.png
[scatter]:./../imgs/modules/pandas_scatter.png
[hexagon]:./../imgs/modules/pandas_hexagon.png

------------------------------------

### SERIES

Series hold data associated to a _Index_.  
The Index can be created from a lists of numbers, strings (like dicts), etc.  
It accepts numpy arrays too.

The _Data_ can be any object.  
It even accept functions.
<!-- --><br/>
<!-- --><br/>


- Create a Series with a List of Data and (optional) a List of Index:

```python
pd.Series( <data-list> )
```
```python
pd.Series( <data-list>, <index-list>)
```
```python
pd.Series(data=<data-list>, index=<index-list>)
```
<!-- --><br/>


- Access a Series´ specific data:

```python
<series>[<index>]
```
<!-- --><br/>


- Add two Series based on Index:
```python
<series> + <series>
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### DATAFRAMES

##### Creating and Adding data

DataFrames hold and manipulate Series.
<!-- --><br/>


- Create a DataFrame:

```python
pd.DataFrame(<data>, <index>, ['<column>', ..., '<column>'])
```
```python
pd.DataFrame(data=<data>, index=<index>, columns=['<column>', ..., '<column>'])
```
<!-- --><br/>


> **Example**
>
> ```python
> df = pd.DataFrame(np.random.randn(5, 4), index='A B C D E'.split(), columns='W X Y Z'.split())
> ```
> This random DataFrame generated was used in most of the examples, so:
> ```python
> data = [[-0.260599, -0.517255, -0.401975, -1.745364],
>         [-0.653223, -1.362995,  0.335261,  0.666447],
>         [ 2.378122, -0.293997,  1.127474, -0.898852],
>         [ 0.636019, -1.455195,  0.855026, -2.206777],
>         [ 0.032626,  0.987973,  0.542521, -0.761312]]
> df = pd.DataFrame(data, index='A B C D E'.split(), columns='W X Y Z'.split())
> ```
> Output:
> ```
>           W         X         Y         Z
> A -0.260599 -0.517255 -0.401975 -1.745364
> B -0.653223 -1.362995  0.335261  0.666447
> C  2.378122 -0.293997  1.127474 -0.898852
> D  0.636019 -1.455195  0.855026 -2.206777
> E  0.032626  0.987973  0.542521 -0.761312
> ```
>---
<!-- --><br/>


- Add a column to a DataFrame:

```python
<dataframe>[ '<new-column>' ] = <series>
```
<!-- --><br/>


- Add a line to the DataFrame:

```python
<dataframe>.loc[ <new-index> ] = <list>
```
<!-- --><br/>
<!-- --><br/>



##### Indexing & Slicing

- Access a column on a DataFrame (returns a Series):
```python
<dataframe>[ '<column>' ]
```
<!-- --><br/>


- Access multiple columns on a DataFrame (returns a DataFrame):

```python
<dataframe>[ ['<column>', ...] ]
```
<!-- --><br/>


- Locate elements:
    - Get all line:
    ```python
    <dataframe>.loc[ <index> ]
    ```
    - Specific element:
    ```python
    <dataframe>.loc[ <index>, '<column>' ]
    ```
    - Multiple lines and/or columns:
    ```python
    <dataframe>.loc[ [<index>, ...], ['<column>', ...] ]
    ```
    <!-- --><br/>


- Locate using Numpy index (i.e. numbers) notation:

```python
<dataframe>.iloc[ <index> ]
```
```python
<dataframe>.iloc[ <index>, <index> ]
```
```python
<dataframe>.iloc[ <index>:<index>, '<column>':'<column>' ]
```
<!-- --><br/>


> **Examples**
> 
> Using the same DataFrame from previous example.
> ```python
> df.loc[ ['A','B'], ['X', 'Y', 'Z'] ]
> ```
> Output:
> ```
>           X         Y         Z
> A -0.517255 -0.401975 -1.745364
> B -1.362995  0.335261  0.666447
> ```
> ---
> ```python
> df.iloc[0:2, 1:4]
> ```
> Output:
> ```
>           X         Y         Z
> A -0.517255 -0.401975 -1.745364
> B -1.362995  0.335261  0.666447
> ```
> ---
<!-- --><br/>
<!-- --><br/>



##### Removing Lines and Columns

- Return a DataFrame without a specific line:
```python
<dataframe>.drop( <index> )
```
```python
<dataframe>.drop( [<index>, ...] )
```
<!-- --><br/>


- Return a DataFrame without a specific column:

```python
<dataframe>.drop( '<column>', axis=1 )
```
```python
<dataframe>.drop( columns= '<column>' )
```
```python
<dataframe>.drop( ['<column>', ...], axis=1 )
```
```python
<dataframe>.drop( columns= ['<column>', ...] )
```
<!-- --><br/>


- Delete a line on a DataFrame:

```python
<dataframe> = <dataframe>.drop( <index> )
```
```python
<dataframe>.drop( <index>, inplace=True )
```
<!-- --><br/>


- Delete a column on a DataFrame:

```python
<dataframe> = <dataframe>.drop('<column>', axis=1)
```
```python
<dataframe>.drop('<column>', axis=1, inplace=True)
```
```python
del <dataframe>.['<column>']
```
<!-- --><br/>
also, if warnings, take a look at this: https://www.dataquest.io/blog/settingwithcopywarning/
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### METHODS & PARAMETERS

##### Methods for Info

- Get info about the DataFrame:

```python
<dataframe>.info()
```
<!-- --><br/>


- Return first `n` rows of the DataFrame (default=5):

```python
<dataframe>.head()
```
```python
<dataframe>.head(<n>)
```
<!-- --><br/>
<!-- --><br/>



##### Methods to modify Index

- Resetting a DataFrame Index to default (numbers) and adding the current as a column:

```python
<dataframe>.reset_index()
```
```python
<dataframe>.reset_index(inplace=True)
```
<!-- --><br/>


- Resetting a DataFrame Index to default (numbers), but don't add current as column:

```python
<dataframe>.reset_index(drop=True)
```
<!-- --><br/>


- Turn a column of a DataFrame into Index:

```python
<dataframe>.set_index('<column>')
```
```python
<dataframe>.set_index('<column>', inplace=True)
```
<!-- --><br/>
<!-- --><br/>



##### Methods for Operations over Index and Columns

- Find the **mean** of the values of a column:

```python
<dataframe>['<column>'].mean()
```
<!-- --><br/>


- Find the **Correlation** among the columns of the DataFrame:

```python
<dataframe>.corr()
```
<!-- --><br/>


- Return the **sum** of all values of a Series:

```python
<series>.sum()
```
```python
<dataframe>['<column>'].sum()
```
<!-- --><br/>


- Return a Series with the **sum** of values on each column of a DataFrame:

```python
<dataframe>.sum()
```
<!-- --><br/>


- Find the **minimum** or **maximum** values of a column:

```python
<dataframe>['<column>'].min()
```
```python
<dataframe>['<column>'].max()
```
<!-- --><br/>


- Find the **minimum** or **maximum** values of every column:

```python
<dataframe>.min()
```
```python
<dataframe>.max()
```
<!-- --><br/>


- Find the Index of the **minimum** or **maximum** values of a column:

```python
<dataframe>['<column>'].idxmin()
```
```python
<dataframe>['<column>'].idxmax()
```
<!-- --><br/>


- Find the Index of the **minimum** or **maximum** values of every column:

```python
<dataframe>.idxmin()
```
```python
<dataframe>.idxmax()
```
<!-- --><br/>


- Return a Numpy Array with only **unique values** (omitting repetition):

```python
<series>.unique()
```
```python
<dataframe>['<column>'].unique()
```
<!-- --><br/>


- Return how many **unique values** there is on a Series:

```python
<series>.nunique()
```
```python
<dataframe>['<column>'].nunique()
```
<!-- --><br/>


- Return a Series with the **count** of elements on each column:

```python
<dataframe>.count()
```
<!-- --><br/>


- Count how many elements have a **specific value** on a column:

```python
sum(<dataframe>.['<column>'] == <value>)
```
<!-- --><br/>


- Return a Series with the **count** of each value:
```python
<series>.value_counts()
```
```python
<dataframe>['<column>'].value_counts()
```

- **Sort** the lines of a DataFrame by some column:

```python
<dataframe>.sort_values(by='<column>')
```
```python
<dataframe>.sort_values(by='<column>', ascending=False)
```
<!-- --><br/>


- Return a DataFrame of bool with what values of a DataFrame are **null**:

```python
<dataframe>.isnull()
```
<!-- --><br/>
<!-- --><br/>



##### Methods for Operations over Values

- Percentage change between the current and a prior element on every column:

```python
<dataframe>.pct_change()
```
<!-- --><br/>

![][pct_change]

<!-- --><br/>

- Mean Rolling Window Calculation:

```python
<series>.rolling(window=<value>).mean()
```
```python
<series>.rolling(window=<value>, center=True).mean()
```

```python
<dataframe>.rolling(window=<value>).mean()
```
```python
<dataframe>.rolling(window=<value>, center=True).mean()
```

```python
<dataframe>.rolling(window=<value>, axis=1).mean()
```
```python
<dataframe>.rolling(window=<value>, axis=1, center=True).mean()
```
<!-- --><br/>


- Sum Rolling Window Calculation:

```python
<series>.rolling(window=<value>).sum()
```
```python
<dataframe>.rolling(window=<value>).sum()
```
```python
<dataframe>.rolling(window=<value>, axis=1).sum()
```

```python
<series>.rolling(window=<value>, center=True).sum()
```
```python
<dataframe>.rolling(window=<value>, center=True).sum()
```
```python
<dataframe>.rolling(window=<value>, axis=1, center=True).sum()
```
<!-- --><br/>
<!-- --><br/>



##### Map and Apply

- Apply a function to all of the elements (similar to Python's map):

```python
<series>.apply(<function>)
```
```python
<series>.apply(<lambda>)
```
```python
<dataframe>.apply(<function>)
```
```python
<dataframe>.apply(<lambda>)
```
```python
<dataframe>[column].apply(<function>)
```
```python
<dataframe>[column].apply(<lambda>)
```
<!-- --><br/>


- Substitute each value in a Series with another value using a 'map' (dict, function or Series):
```python
<series>.map(<map>)
```
```python
<dataframe>['<column>'].map(<map>)
```
<!-- --><br/>
<!-- --><br/>



##### Misc Methods

- Convert a datetime-like object (datetime, List, Array-like, ...), or a Series with it, to Timestamp:

```python
pd.to_datetime(<series>)
```
```python
pd.to_datetime(<datetime-like-obj>)
```
<!-- --><br/>


- Timestamp parameters:

```python
<timestamp>.tz          # timezone
<timestamp>.tzinfo
<timestamp>.year
<timestamp>.month
<timestamp>.day
<timestamp>.weekday
<timestamp>.hour
<timestamp>.minute
<timestamp>.second
<timestamp>.microsecond
<timestamp>.nanosecond
```
<!-- --><br/>


- Get a generator which yields both the Index and Row (as a Series):

```python
<dataframe>.iterrows()
```
<!-- --><br/>

- See 2nd answer [here][panda-iter] for _why not to do that_.
<!-- --><br/>

[panda-iter]:https://stackoverflow.com/questions/16476924/how-to-iterate-over-rows-in-a-dataframe-in-pandas "How to iterate over rows in a DataFrame in Pandas?"


> **Example**
> ```python
> df = pd.DataFrame({'c1': [10, 11, 12], 'c2': [100, 110, 120]})
> 
> df.head()
> 
> for index, row in df.iterrows():
>     print(row['c1'], row['c2'])
> ```
> Output:
> ```python
>    c1   c2
> 0  10  100
> 1  11  110
> 2  12  120
>
> 10 100
> 11 110
> 12 120
> ```
> ---

<!-- --><br/>
<!-- --><br/>



##### Parameters

- Diplay a Series Index:

```python
<series>.index
```
<!-- --><br/>


- Return a Numpy Array with a Series values:

```python
<series>.values
```
<!-- --><br/>


- Display the Index of a DataFrame:

```python
<dataframe>.index
```
<!-- --><br/>


- Display the Columns of a DataFrame:

```python
<dataframe>.columns
```
<!-- --><br/>


- Display the Index's names of a DataFrame:

```python
<dataframe>.index.names
```
<!-- --><br/>


- Return the Shape of a DataFrame (tuple with number of lines and columns):

```python
<dataframe>.shape
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### BOOLEAN OPERATIONS & FILTERS

- Boolean expressions can be applied directly on DataFrames (just like in Numpy Arrays) to be checked for all of it's elements.

- Example:
  Return a DataFrame of Booleans for each element equal to a value:

```python
<dataframe>  ==  <value>
```
<!-- --><br/>
<!-- --><br/>



##### Filter

- It is possible to use this DataFrame of Booleans to Filter a DataFrame of same shape.  
  Instead of being removed (like on Numpy Arrays), values filtered by this method are substituted by `NaN` (Not a Number).

<!-- --><br/>


- Use an DataFrame of Booleans to extract specific elements from a DataFrame of same shape:

```python
<dataframe>[<bool-dataframe>]
```
<!-- --><br/>
<!-- --><br/>



> **Examples**
>
> ```python
> df > 0
> ```
>
> Output:
> ```
>        W      X      Y      Z
> A  False  False  False  False
> B  False  False   True   True
> C   True  False   True  False
> D   True  False   True  False
> E   True   True   True  False
> ```
> ---
>
> ```python
> df[ df > 0 ]
> ```
>
> Output:
> ```
>           W         X         Y         Z
> A       NaN       NaN       NaN       NaN
> B       NaN       NaN  0.335261  0.666447
> C  2.378122       NaN  1.127474       NaN
> D  0.636019       NaN  0.855026       NaN
> E  0.032626  0.987973  0.542521       NaN
> ```
> ---

<!-- --><br/>



- It is also possible to filter specific lines using a Series of Booleans.  
  In this case, the lines filtered are removed.

<!-- --><br/>

- Return a Series of Booleans for each element bigger than a value on the column:

```python
<dataframe> ['<column>']  >  <value>
```
<!-- --><br/>


- Use an Series of Booleans to omit a specific line from a DataFrame:

```python
<dataframe>[<bool-series>]
```
<!-- --><br/>


> **Examples**
>
> ```python
> df['W'] > 0
> ```
> 
> Output:
> ```
> A    False
> B    False
> C     True
> D     True
> E     True
> ```
> ---
>
> ```python
> df[ df['W'] > 0 ]
> ```
>
> Output:
> ```
>           W         X         Y         Z
> C  2.378122 -0.293997  1.127474 -0.898852
> D  0.636019 -1.455195  0.855026 -2.206777
> E  0.032626  0.987973  0.542521 -0.761312
> ```
> ---

<!-- --><br/>
<!-- --><br/>



##### Multiple Filters

- It is also possible to use multiple conditions by putting the expressions in parenthesis and using the operators:

|   Operators   |   Python's Equivalent   |
| :----: | :----: |
|   `&`   |   `and`   |
|   `|`   |   `or`   |
|   `~`   |   `not`   |
<!-- --><br/>


- Example:  
  Return a Series of Booleans for each element bigger than a value on the column and smaller on the other column:

```python
(<dataframe> ['<column>']  >  <value>) & (<dataframe> ['<column>']  <  <value>)
```
<!-- --><br/>


> **Examples**
>
> ```python
> (df['W'] > 0)  &  (df['X'] < 0)
> ```
> 
> Output:
> ```
> A    False
> B    False
> C     True
> D     True
> E    False
> ```
> ---
>
> ```python
> df[ (df['W'] > 0)  &  (df['X'] < 0) ]
> ```
>
> Output:
> ```
>           W         X         Y         Z
> C  2.378122 -0.293997  1.127474 -0.898852
> D  0.636019 -1.455195  0.855026 -2.206777
> ```
> ---

<!-- --><br/>
<!-- --><br/>



- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### MULTIINDEX (HIERARCHICAL INDEX) & NAMES


##### Hierarchical Index

- Both Series and DataFrame can have multiple 'levels', having different Index for different levels.  
  For that, a MultiIndex object must be used as Index.

- Create a MultiIndex from a List of Tuples:

```python
pd.MultiIndex.from_tuples(<tuple-list>)
```
<!-- --><br/>


- Create a MultiIndex from a List of Arrays:

```python
pd.MultiIndex.from_arrays(<array-list>)
```
<!-- --><br/>


- Create a MultiIndex from a DataFrame:

```python
pd.MultiIndex.from_frame(<dataframe>)
```
<!-- --><br/>


- Make MultinIndex DataFrame:

```python
pd.DataFrame(<data>, index=<multiindex>, <columns>)
```
<!-- --><br/>


- Make MultinIndex-Columns DataFrame:

```python
pd.DataFrame(<data>, <index>, columns=<multiindex>)
```
<!-- --><br/>


> **Examples**
>
> ```python
> outside = ['G1','G1','G1','G2','G2','G2']
> inside = [1,2,3,1,2,3]
> hier_index = list(zip(outside,inside))
> 
> hier_index = pd.MultiIndex.from_tuples(hier_index)
> 
> df = pd.DataFrame(np.random.randn(6, 2), index=hier_index, columns='A B'.split())
> ```
> 
> Output:
> ```
>              A         B
> G1 1 -1.953677 -0.706516
>    2 -0.351613  0.285850
>    3  1.144663 -1.750029
> G2 1 -0.618488 -1.755436
>    2  0.215214 -0.145591
>    3 -0.283904 -1.760282
> ```
> ---
>
> ```python
> df.loc['G1']
> ```
>
> Output:
> ```
>           A         B
> 1 -1.953677 -0.706516
> 2 -0.351613  0.285850
> 3  1.144663 -1.750029
> ```
> ---

<!-- --><br/>
<!-- --><br/>



##### Name

- The Index of DataFrames have 'names' to identify them.  
  Using the Names, it is possible make cross-section (`xs`) to select lines with same index on a specific level.

<!-- --><br/>


- Create a MultiIndex with Names:

```python
pd.MultiIndex.from_tuples(<tuple-list>, names=['<name>', ..., '<name>'])
```
```python
pd.MultiIndex.from_arrays(<array-list>, names=['<name>', ..., '<name>'])
```
```python
pd.MultiIndex.from_frame (<dataframe>,  names=['<name>', ..., '<name>'])
```
<!-- --><br/>


- Display the Index's Names:

```python
<dataframe>.index.names
```
<!-- --><br/>


- Display the Columns' Names:

```python
<dataframe>.columns.names
```
<!-- --><br/>


- Add names to a existing DataFrame:

```python
<dataframe>.index.names = ['<name>', ...]
```
```python
<dataframe>.columns.names = ['<name>', ...]
```
<!-- --><br/>
<!-- --><br/>



##### Cross-Sections

- Cross-section all Index labels of a level:

```python
df.xs(<index>)
```
```python
df.xs(<index>, level='<name>')
```
<!-- --><br/>


- Cross-section all Column labels of a level:

```python
df.xs(<index>, axis=1)
```
```python
df.xs(<index>, axis=1, level='<name>')
```
<!-- --><br/>
<!-- --><br/>



> **Examples**
>
> ```python
> df.index.names = ['Group', 'Number']
> ```
> 
> Output:
> ```
>                      A         B
> Group Number                    
> G1    1      -1.565060 -0.195813
>       2      -0.329907 -0.923693
>       3      -1.288969 -0.260080
> G2    1       1.547195  0.041312
>       2      -1.670262 -1.058485
>       3      -1.017790 -0.411298
> ```
> ---
>
> ```python
> df.xs('G1')
> ```
> 
> Output:
> ```
>                A         B
> Number                    
> 1      -1.565060 -0.195813
> 2      -0.329907 -0.923693
> 3      -1.288969 -0.260080
> ```
> ---
>
> ```python
> df.xs(1, level='Number')
> ```
> 
> Output:
> ```
>               A         B
> Group                    
> G1    -1.565060 -0.195813
> G2     1.547195  0.041312
> ```
> ---

<!-- --><br/>
<!-- --><br/>



- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### PIVOT TABLE

- Making a Pivot Table from a DataFrame using:
  - the **values** of a column as data;
  - a column (or columns, MultiIndex) as name(s) and its values as **index**;
  - the values of a column as **columns**.

```python
<dataframe>.pivot_table(values=<colums>, index=['<column>', ...], columns=['<column>', ...])
```
<!-- --><br/>


> **Examples**
>
> ```python
> data = {'A':['foo','foo','foo','bar','bar','bar'],
>         'B':['one','one','two','two','one','one'],
>         'C':['x','y','x','y','x','y'],
>         'D':[1,3,2,5,4,1]}
>
> df = pd.DataFrame(data)
> ```
> 
> Output:
> ```
>      A    B  C  D
> 0  foo  one  x  1
> 1  foo  one  y  3
> 2  foo  two  x  2
> 3  bar  two  y  5
> 4  bar  one  x  4
> 5  bar  one  y  1
> ```
> ---
>
> ```python
> df.pivot_table(values='D',index=['A', 'B'],columns=['C'])
> ```
> 
> Output:
> ```
>      A    B  C  D
> 0  foo  one  x  1
> 1  foo  one  y  3
> 2  foo  two  x  2
> 3  bar  two  y  5
> 4  bar  one  x  4
> 5  bar  one  y  1
> ```
> ---

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### MISSING DATA

- Return a DataFrame omiting the axis (default=0) with data missing:

```python
<dataframe>.dropna()
```
```python
<dataframe>.dropna(axis=1)
```
<!-- --><br/>


- Omit missing data from a threshold quantity of missing data and above:

```python
<dataframe>.dropna(thresh=<value>)
```
<!-- --><br/>


- Return a DataFrame filling all missing data with some value:

```python
<dataframe>.fillna(value=<value>)
```
<!-- --><br/>


- Return a DataFrame filling each missing value with the value before it (forward-fill method):

```python
<dataframe>.fillna(method='ffill')
```
<!-- --><br/>


- Fill the missing values on a column of a DataFrame wtih the mean of the column:

```python
<dataframe>.fillna(value=<dataframe>['<column>'].mean())
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### GROUP BY


- The idea is to group all items of a specific column if they follow a condition, and then, make an operation on a different column.  
  For this, a Group object is created, in which we make the operations.

<!-- --><br/>



- Create a Group object by some column:

```python
<dataframe>.groupby('<column>')
```
```python
<dataframe>.groupby(['<column>', ...])
```
<!-- --><br/>
<!-- --><br/>



##### Methods

- Only after Applying one of those methods on the Group object a DataFrame is returned.

<!-- --><br/>

- Show a description (with many methods aplied) of the Group:

```python
<group>.describe()
```
<!-- --><br/>

- Count values on Group:

```python
<group>.count()
```
<!-- --><br/>

- Sum all values from a Group:

```python
<group>.sum()
```
<!-- --><br/>

- Get the mean of all values from a Group:

```python
<group>.mean()
```
<!-- --><br/>

- Get the std of all values from a Group:

```python
<group>.std()
```
<!-- --><br/>

- Get the minimum of all values from a Group:

```python
<group>.min()
```
<!-- --><br/>

- Get the maximun of all values from a Group:

```python
<group>.max()
```
<!-- --><br/>
<!-- --><br/>



> **Examples**
>
> ```python
> codata = {'Empresa':['GOOG','GOOG','MSFT','MSFT','FB','FB'],
>          'Nome':['Sam','Charlie','Amy','Vanessa','Carl','Sarah'],
>          'Venda':[200,120,340,124,243,350]}
> 
> df = pd.DataFrame(data)de
> ```
> 
> Output:
> ```
>   Empresa     Nome  Venda
> 0    GOOG      Sam    200
> 1    GOOG  Charlie    120
> 2    MSFT      Amy    340
> 3    MSFT  Vanessa    124
> 4      FB     Carl    243
> 5      FB    Sarah    350
> ```
> ---
>
> ```python
> g = df.groupby('Empresa')
> g.sum()
> ```
> 
> Output:
> ```
>          Venda
> Empresa       
> FB         593
> GOOG       320
> MSFT       464
> ```
> ---
>
> ```python
> g.describe()
> ```
> 
> Output:
> ```
>         Venda                                                        
>         count   mean         std    min     25%    50%     75%    max
> Empresa                                                              
> FB        2.0  296.5   75.660426  243.0  269.75  296.5  323.25  350.0
> GOOG      2.0  160.0   56.568542  120.0  140.00  160.0  180.00  200.0
> MSFT      2.0  232.0  152.735065  124.0  178.00  232.0  286.00  340.0
> ```
> ---

<!-- --><br/>
<!-- --><br/>



##### Unstack

- A Series with MultiIndex can be Unstacked into a DataFrame:

```python
<series>.unstack()
```
```python
<dataframe>[<column].unstack()
```
<!-- --><br/>
<!-- --><br/>



> **Examples**
>
> ```python
> df = pd.read_csv('./../misc/files/911.csv')
> 
> df['department'] = df['title'].apply(lambda ttl: ttl.split(': ')[0])
> 
> df['timeStamp'] = pd.to_datetime(df['timeStamp'])
> df['hour'] = df['timeStamp'].apply(lambda time: time.hour)
> df['dWeek'] = df['timeStamp'].apply(lambda time: time.weekday())
> 
> df.groupby(by=['dWeek','hour']).count()['department'].unstack().head()
> ```
> 
> Output: 
> ```python
> hour    0    1    2    3    4    5    6    7    8    9    10  ...   13   14   15    16    17   18   19   20   21   22   23
> dWeek                                                         ...                                                         
> 0      282  221  201  194  204  267  397  653  819  786  793  ...  842  869  913   989   997  885  746  613  497  472  325
> 1      269  240  186  170  209  239  415  655  889  880  840  ...  917  943  938  1026  1019  905  731  647  571  462  274
> 2      250  216  189  209  156  255  410  701  875  808  800  ...  872  904  867   990  1037  894  686  668  575  490  335
> 3      278  202  233  159  182  203  362  570  777  828  837  ...  936  876  969   935  1013  810  698  617  553  424  354
> 4      275  235  191  175  201  194  372  598  742  752  803  ...  890  932  980  1039   980  820  696  667  559  514  474
> ```
> ---

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### CONCATENATE, MERGE & JOIN


##### Concatenate

- To Concatenate DataFrames, the axis referent to the operation must have same size.  
  If the DataFrames don't have the same index on the axis of operation they will be added to the resulting DataFrame.

<!-- --><br/>

- Return a Dataframe from multiple DataFrames concatenated by lines (default: axis = 0):

```python
pd.concat([<dataframe>, ...])
```
<!-- --><br/>

- Return a Dataframe from multiple DataFrames concatenated by columns (axis = 1):

```python
pd.concat([<dataframe>, ...], axis=1)
```
<!-- --><br/>


- Make a DataFrame with Hierarchial Columns:

```python
keys= ['<df-titles>', ...]
names= ['<name-higher-level>', '<name-lower-level>']

pd.concat([<dataframe>, ...], <keys>, <names>)
```
<!-- --><br/>



> **Examples**
>
> ```python
> df1 = pd.DataFrame({'A': ['A0', 'A1'],
>                     'B': ['B0', 'B1'],})
> ```
> 
> Output:
> ```
>     A   B
> 0  A0  B0
> 1  A1  B1
> ```
> ---
>
> ```python
> df2 = pd.DataFrame({'A': ['A2', 'A3'],
>                     'B': ['B2', 'B3'],},
> 					index=[2,3])
> ```
> 
> Output:
> ```
>     A   B
> 2  A2  B2
> 3  A3  B3
> ```
> ---
>
> ```python
> pd.concat([df1,df2])
> ```
> 
> Output:
> ```
>     A   B
> 0  A0  B0
> 1  A1  B1
> 2  A2  B2
> 3  A3  B3
> ```
> ---
>
> ```python
> pd.concat([df1,df2], axis=1)
> ```
> 
> Output:
> ```
>      A    B    A    B
> 0   A0   B0  NaN  NaN
> 1   A1   B1  NaN  NaN
> 2  NaN  NaN   A2   B2
> 3  NaN  NaN   A3   B3
> ```
> ---
>
> ```python
> df2.reset_index(drop=True)
> pd.concat([df1,df2], axis=1)
> ```
> 
> Output:
> ```
>     A   B   A   B
> 0  A0  B0  A2  B2
> 1  A1  B1  A3  B3
> ```
> ---
>
> ```python
> pd.concat([df1,df2], axis=1, keys=['df1', 'df2'], names=['DataFrames','columns'])
> ```
> 
> Output:
> ```
> DataFrames df1     df2    
> columns      A   B   A   B
> 0           A0  B0  A2  B2
> 1           A1  B1  A3  B3
> ```
> ---

<!-- --><br/>
<!-- --><br/>



##### Merge

- The Merge method joins TWO DataFrames given they have some equal values on some column(s).
- The Merge method have a `how` parameter that specifies the type of merge performed:

<!-- --><br/>

|  how =  | Description |
| :-----: | :---------: |
| `inner` | Use intersection of keys from both frames (default) |
| `outer` | Use union of keys from both frames |
| `left`  | Use only keys from left frame |
| `right` | Use only keys from right frame |

<!-- --><br/>

- Return DataFrame merging all Similar columns:

```python
pd.merge(<left-dataframe>, <right-dataframe>)
```
```python
pd.merge(<left-dataframe>, <right-dataframe>, how='<merge-type>')
```
<!-- --><br/>

- Return DataFrame merging just the specified columns:

```python
pd.merge(<dataframe>, <dataframe>, on='<column>')
```
```python
pd.merge(<dataframe>, <dataframe>, on=['<column>', ...])
```
<!-- --><br/>
<!-- --><br/>



##### Join

- The Join method (unlike the previous two) is a DataFrame's method.  
  It tries to join DataFrame that have possibly different index.  
  It has the same types of 'merge' as the Merge method (default: `how='left'`).

<!-- --><br/>

- Join a Dataframe to another:

```python
<left-dataframe>.join(<right-dataframe>)
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### INPUT & OUTPUT DATA

> **Note**
> 
> On Jupyter or IPython you can see all possible Input methods by typing and pressing [tab]:
>
> ```python
> pd.read_
> ```
> 
> Pressing Tab:
> ```
> pd.read_clipboard(  pd.read_feather(    pd.read_hdf(        pd.read_orc(        pd.read_sas(        pd.read_sql_query(  pd.read_table(      
> pd.read_csv(        pd.read_fwf(        pd.read_html(       pd.read_parquet(    pd.read_spss(       pd.read_sql_table(  
> pd.read_excel(      pd.read_gbq(        pd.read_json(       pd.read_pickle(     pd.read_sql(        pd.read_stata(
> ```
> ---

<!-- --><br/>
<!-- --><br/>



##### File '.csv'


- Create a DataFrame from a CSV file:

```python
pd.read_csv('<filepath>')
```
<!-- --><br/>


- Specify the column to be used as index:

```python
pd.read_csv('<filepath>', index_col='<column>')
```
<!-- --><br/>


- Specify a separator (from element to element):

```python
pd.read_csv('<filepath>', sep='<separator>')
```
<!-- --><br/>


- Specify decimal marker:

```python
pd.read_csv('<filepath>', decimal='<decimal>')
```
<!-- --><br/>


- Export DataFrame to a CSV file:

```python
<dataframe>.to_csv('<filepath>', sep='<separator>', decimal='<decimal>')
```
<!-- --><br/>
<!-- --><br/>



> **Examples**
>
> `exemplo.csv`:
> ```
> a,b,c,d
> 0,1,2,3
> 4,5,6,7
> 8,9,10,11
> 12,13,14,15
> ```
> ---
>
> ```python
> df = pd.read_csv('exemplo', sep=',')
> df
> ```
> 
> Output:
> ```
>     a   b   c   d
> 0   0   1   2   3
> 1   4   5   6   7
> 2   8   9  10  11
> 3  12  13  14  15
> ```
> ---
>
> ```python
> df.to_csv('exemplo2.csv', sep=';', decimal=',')
> ```
> ---
>
> `exemplo2.csv`:
> ```
> ;a;b;c;d
> 0;0;1;2;3
> 1;4;5;6;7
> 2;8;9;10;11
> 3;12;13;14;15
> ```
> ---

<!-- --><br/>
<!-- --><br/>



##### File '.xlsx'


- Import a Sheet from a Excel (.xlsx) file:

```python
pd.read_excel('<filepath>', sheetname='<sheet>')
```
<!-- --><br/>


- Export to a Excel file:

```python
<dataframe>.to_excel(<filepath>, sheet_name='<sheet>')
```
<!-- --><br/>
<!-- --><br/>



##### File '.html'


- Import a Table on HTML in a url (returns a list where the DataFrame(s) will be elements of it):

```python
pd.read_html('<url>')
```
<!-- --><br/>
<!-- --><br/>



##### Cool Image


- Export a really cool image (png) of the DataFrame:

```python
import dataframe_image as dfi
dfi.export(<dataframe>, '<filepath>.png')
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### DATA VISUALIZATION

> **Note**
> 
> All of those Plots return matplotlib's Axes.
> 
> ---

<!-- --><br/>
<!-- --><br/>



- Imports:

```python
import matplotlib.pyplot as plt
```



##### Simple Plot


- Simple graph:

```python
<dataframe>['<column>'].plot()
```
<!-- --><br/>


- Command Explanation:

```python
<dataframe>['<column>'].plot(rot=<degrees>)
```
<!-- --><br/>
<!-- --><br/>



##### Histogram


- Plot a Histogram of a column:

```python
<dataframe>['<column>'].hist()
```
```python
<dataframe>['<column>'].hist(bins=<bins>)
```
<!-- --><br/>
<!-- --><br/>



##### Lines


- Plot Lines:

```python
<dataframe>.plot.line(y='<column>')
```
```python
<dataframe>.plot.line(y='<column>', lw=<value>)
```
```python
<dataframe>.plot.line(y='<column>', figsize=( <width>, <height> ))
```
<!-- --><br/>
<!-- --><br/>


> **Examples**
>
> ```python
> df1 = pd.read_csv('./../misc/files/df1.csv', index_col=0)
> df1.plot.line(y='B', lw=1, figsize=(12,5))
> plt.show()
> ```
> 
> Output:
> 
> ![][lines]
> 
> ---

<!-- --><br/>
<!-- --><br/>



##### Stacked Area Plot


- Plot a Stacked Area:

```python
<dataframe>.plot.area()
```
```python
<dataframe>.plot.area(alpha=<value>)
```
<!-- --><br/>
<!-- --><br/>


> **Examples**
>
> ```python
> plt.style.use('bmh')
> plt.style.use('dark_background')
> 
> df2 = pd.read_csv('./../misc/files/df2.csv')
> df2.plot.area(alpha=.5)
> plt.show()
> ```
> 
> Output:
> 
> ![][stacked_area]
> 
> ---

<!-- --><br/>
<!-- --><br/>



##### Bars


- Plot Bars:

```python
<dataframe>.plot.bar()
```
<!-- --><br/>


- Plot Stacked Bars:

```python
<dataframe>.plot.bar(stacked=True)
```
<!-- --><br/>
<!-- --><br/>



##### Scatter


- Make a Scatter Plot:

```python
<dataframe>.plot.scatter(x='<column>', y='<column>')
```
<!-- --><br/>


- Define color of the point using another column:

```python
<dataframe>.plot.scatter(x='<column>', y='<column>', c='<column>')
```
<!-- --><br/>


- Define size of the point using another column:

```python
<dataframe>.plot.scatter(x='<column>', y='<column>', s=<dataframe>['<column>'])
```
<!-- --><br/>
<!-- --><br/>


> **Examples**
>
> ```python
> import matplotlib.pyplot as plt
> df1.plot.scatter(x='A', y='B', s=df1['C']*50, c='C', cmap='coolwarm')
> plt.show()
> ```
> 
> Output:
> 
> ![][scatter]
> 
> ---

<!-- --><br/>
<!-- --><br/>



##### Box Plot


- Make Box Plot:

```python
<dataframe>.plot.box()
```
<!-- --><br/>
<!-- --><br/>



##### Hexagon Plot


- Make Hexagon Plot:

```python
<dataframe>.plot.hexbin(x='<column>', y='<column>')
```
```python
<dataframe>.plot.hexbin(x='<column>', y='<column>', gridsize=<value>)
```
```python
<dataframe>.plot.hexbin(x='<column>', y='<column>', cmap=<colormap>)
```
<!-- --><br/>
<!-- --><br/>


> **Examples**
>
> ```python
> import numpy as np
> df = pd.DataFrame(np.random.rand(1000,2), columns='A B'.split())
> df.plot.hexbin(x='A', y='B', gridsize=20, cmap='Oranges')
> plt.show()
> ```
> 
> Output:
> 
> ![][hexagon]
> 
> ---

<!-- --><br/>
<!-- --><br/>



##### Kernel Density Estimation


- Make KDE Plot:

```python
<dataframe>.plot.kde()
```
```python
<dataframe>['<column>'].plot.kde()
```
<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------

### DATAREADER


- Functions from pandas_datareader.data and pandas_datareader.wb extract data from various Internet sources into a pandas DataFrame.
<!-- --><br/>

- Supports:
  - Google Finance,
  - St. Louis FED (FRED),
  - Kenneth French's data library,
  - ...
<!-- --><br/>
<!-- --><br/>



- Imports:
```python
from pandas_datareader import data, wb
import datetime
```
<!-- --><br/>
<!-- --><br/>



- Get data of a Bank, from a Internet Source, from a specific period.

```python
<datetime> = datetime.datetime(<year>, <month>, <day>)
data.DataReader(name='<ticker>', <data_source>, start=<datetime>, end=<datetime>)
```

- `data_source=`
  - `"stooq"`
  - `"yahoo"`
  - ...

- [List of Bank and tickers](https://topforeignstocks.com/stock-lists/the-complete-list-of-bank-stocks-trading-on-the-nyse-2/)

|`'<ticker>'`| Bank name |
| :--------: | --------- |
|   'BAC'    | Bank of America |
|   'C'      | Citigroup Inc. |
|   'GS'     | Goldman Sachs |
|   'JPM'    | JP Morgan Chase & Co. |
|   'MS'     | Morgan Stanley |
|   'WFC'    | Wells Fargo & Company |
|     ...    | ... |
<!-- --><br/>
<!-- --><br/>


> **Examples**
>
> ```python
> start = datetime.datetime(2006, 1, 1)
> end = datetime.datetime(2016, 1, 1)
> 
> # Bank of America
> BAC = data.DataReader("BAC", 'yahoo', start, end)
> 
> # CitiGroup
> C = data.DataReader("C", 'yahoo', start, end)
> 
> # Goldman Sachs
> GS = data.DataReader("GS", 'yahoo', start, end)
> 
> # JPMorgan Chase
> JPM = data.DataReader("JPM", 'yahoo', start, end)
> 
> # Morgan Stanley
> MS = data.DataReader("MS", 'yahoo', start, end)
> 
> # Wells Fargo
> WFC = data.DataReader("WFC", 'yahoo', start, end)
> ```
> ---

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------



------------------------------------



------------------------------------



------------------------------------



------------------------------------



------------------------------------



------------------------------------



------------------------------------



------------------------------------

### TOPIC <!-- omit in toc -->

> **Note**
> 
> note
> 
> ---
>
> :warning: **WARNING :**
>
> Warning

<!-- --><br/>
<!-- --><br/>



##### Subtopic <!-- omit in toc -->


- Command Explanation:

```python
command
```
```python
alternative command
```
<!-- --><br/>


- Command Explanation:

```python
command
```
<!-- --><br/>
<!-- --><br/>



##### Subtopic <!-- omit in toc -->


- Command Explanation:

```python
command
```
<!-- --><br/>
<!-- --><br/>


> **Examples**
>
> ```python
> code
> ```
> 
> Output:
> ```
> code
> ```
> ---

<!-- --><br/>
<!-- --><br/>


- Go back to [TABLE OF CONTENT](#table-of-content).
<!-- --><br/>



------------------------------------



------------------------------------



------------------------------------



------------------------------------




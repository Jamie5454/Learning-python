# Day 15

## Delete data

``` python
import pandas as pd
local = 'C:/pandas/delete.xlsx'
data = pd.read_excel(local,index_col='index')
print(data.drop(labels=[1,3])) #delete row1 and row3
print(data.drop('subjetc1',axis=1)) #delete column subject1
print(data.drop(labels=['subjetc1','subject2'],axis=1)) 

```

## NaN

``` python 
import pandas as pd
local = 'C:/pandas/delete.xlsx'
data = pd.read_excel(local,index_col='index')
```

#### using format

DataFrame.dropna(axis=0,how='any'/"all",thresh=10,subset=['subject1'])

* **"any"** have NaN delete 

* **"all"** all NaN delete  

* **thresh**=10 non NaN<10  subset 

* **Specify** column

## Fill

``` py
import pandas as pd
local = 'C:/pandas/delete.xlsx'
data = pd.read_excel(local,index_col='index')
```

#### using format

DataFrame.fillna({'subject1':0.1,'subject2':0.2},limit）

method=‘ffill'/'bfill'

* "ffill" follow the upper one
* "bfill"follow the bottom one

## statistical method

``` python
import pandas as pd
local = 'C:/pandas/test.xlsx'
data = pd.read_excel(local,index_col='index')
print(data.describe())
"""
            point
count    3.000000
mean   593.333333
std      6.806859
min    588.000000
25%    589.500000
50%    591.000000
75%    596.000000
max    601.000000
"""
```

## de-duplication

``` python
import pandas as pd
路径 = 'c:/pandas/duplication.xlsx'
数据 = pd.read_excel(路径,index_col='index')
print(数据.drop_duplicates(subset=['name'],keep='first'))
```

DataFrame.drop_duplicates(subset=None, keep='first', inplace=False)

* subset: to specify a specific column, default is all columns
* keep: Specifies the method to handle duplicate values. 

* first: keeps the first occurrence of the value

* last: Keeps the last occurrence of the value

* False: removes all duplicate values, leaving the ones that have not been duplicated

* inplace: whether to modify directly on the original data or keep a copy
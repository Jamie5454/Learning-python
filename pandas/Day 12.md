# Day 12

## Pandas  （pd)

### class 

* pd.to_csv

* pd.to_excel

* pd.to_sql

### create a file

```python
import pandas as pd
local = 'c:/pandas/myg.xlsx'
file = pd.DataFrame({'order_number':[1,2,3],'order_pirce':[10,20,30]})
file = file.set_index("order_number")
file.to_excel(local)


```

### Read a file

* read_csv #use ","

* read_table  #use "/n"

  ## Basic

* ```python
  import pandas as pd
  local = 'c:/pandas/lxy.txt'
  read_file = pd.read_table(local,sep=',')  
  print(read_file)
  print(read_file.head(3)) #top three rows of data
  print(read_file.shape) #row & column
  print(read_file.column) #topic
  print(read_file.dtype)  #type
  ```

### some propertie

* Sep ="\s+" space or regular expression

* create 

* header

* index_col
* skiprows
* encoding ='utf-8'
* nrows same with .head()



``` python
import pandas as pd
local = 'c:/pandas/lxy.txt'
read_file = pd.read_table(local,sep=',')  

read_file = pd.read_table(local,header=None,names=['header1','header2','header3'],index_col='header3',skiprows[2,3])  
```

### Link to MySQL

import pymysql

```python
import pymysql
import pandas as pd
a = pymysql0.connect(host =,user =,password=,database=)
read_mysql = pd.read_sql('select * from list1',con=a)
```

### Modify Excel

```python
import pandas as pd
local = 'C:/pandas/read.xlsx'
read = pd.read_excel(local,header=None,names=['header1','header2','header3'],index_col='header3')
print(read)
read.to_excel(local)
```

### Series & DataFrame

* ==Series== is one-dimension data: one row or one column

  

```python
import pandas as pd
series = pd.Series(['name','gender','data of birth'])
series_1 =pd.Series{'name':'lxy','gender':'male','data of birth':1996}
list1=['name','gender','data of birth']
list2=['lxy','male','1996']
series_2 = pd.Series(list2,index=list1)
print(series.index) #RangeIndex(start=0, stop=3, step=1)
```

.sort_index()&.sort_values()('rows2'))&

.isnull()&.notnull()

* ==DataFrame== is two-dimensions data: whole table

  Diction and List can both use for creating Series (using list, autofill an index  ):

  ```python
  import pandas as pd
  Data_frame = pd.DataFrame([[1,2,3],[4,5,6],[7,8,9]],columns=['a','b','c'])
  print(Data_frame)
     a  b  c
  0  1  2  3
  1  4  5  6
  2  7  8  9
  print(Data_frame.loc[0]['a'])   #1,   row 0 column 'a'
  print(Data_frame.iloc[0][0])    #1 only about locations
  print(Data_frame[['a','b']]) # a b columns
  ```

### another way of creating a dataframe

```python
import pandas as pd
data1 = pd.Series(['Jamie','Una','Jason'],index=[1,2,3],name ='name')
data2 =pd.Series(['M','F','M'],index=[1,2,3],name ='gender')
data3 =pd.Series(['25','24','24'],index=[1,2,3],name ='age')
frame = pd.DataFrame({data1.name:data1,data2.name:data2,data3.name:data3})
frame = pd.DataFrame([data1,data2,data3])
print(frame)
```

.head() .tail() .index() .values() .shape() .fillna()
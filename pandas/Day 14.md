# Day 14

## Fill tables

```python
import pandas as pd
import datetime as dt
local = 'C:/pandas/fill.xlsx'
data = pd.read_excel(local,index_col='index')
print(data)
"""
         name  price  number  sum
index                            
1       apple      5       5  NaN
2         pen     10       5  NaN
3      banana      3       5  NaN

"""

import pandas as pd
import datetime as dt
local = 'C:/pandas/fill.xlsx'
data = pd.read_excel(local,index_col='index')
data['sum']=data['price']*data['number']
print(data)
"""
         name  price  number  sum
index                            
1       apple      5       5   25
2         pen     10       5   50
3      banana      3       5   15

"""
#using for i in range（1，3）   can skip 2 rows
```

## apply Function

```python
import pandas as pd
def increase_price(x):
    return x+3
local = 'C:/pandas/fill.xlsx'
data = pd.read_excel(local,index_col='index')
data['price']=data['price'].apply(increase_price)
data['price']=data['price'].apply(lambda x:x+3)
print(data)
```

```python
f=lambda a,b,c,d:a*b*c*d
print(f(1,2,3,4))   #24
```

```python
import pandas as pd
local = 'C:/pandas/test.xlsx'
data = pd.read_excel(local,index_col='index')
print(data)
"""
        class  point
index               
1       first    591
2      second    588
3       thrid    601
"""
import pandas as pd
local = 'C:/pandas/test.xlsx'
data = pd.read_excel(local,index_col='index')
data['bonus'] = data['class'].apply(lambda x:5 if x != 'first' else 0)
print(data)

"""
        class  point  bonus
index                      
1       first    591      0
2      second    588      5
3       thrid    601      5
"""
```

```python
import pandas as pd
import numpy as np
arr = np.arange(9).reshape(3,3)
data = pd.DataFrame(arr,columns=list('xyz'),index=list(abc))
print(list('xyz')) #['x', 'y', 'z']
print(data)
"""
   x  y  z
a  0  1  2
b  3  4  5
c  6  7  8
"""
print(data.apply(np.square))
"""
    x   y   z
a   0   1   4
b   9  16  25
c  36  49  64
"""
print(data.apply(lambda x:np.square(x) if x.name=='x' else x))
"""   
    x  y  z
a   0  1  2
b   9  4  5
c  36  7  8
"""
```

## data sort

.sort_value(by="name",inplace=True,ascending=False)

inplace = True : do not create a new 

.sort_index() ：sort by index number

.axis=1 : horizontal row



## data search

``` python
import pandas as pd
local = 'c:/pandas/search.xlsx'
data = pd.read_excel(local,index_col= 'data of birth')
print(data.loc["1983-10-27":'1990-12-31',['Math','Sciences']]) #print this info
print(data.loc[(data['Math']>=60)&(data['Sciences']<=60)])#multi condition
data.loc[data['gender']=='male','call']='sir'
data.loc[data['gender']=='female','call']='Madam'
```

## data screening

```python
import pandas as pd
local = 'C:/pandas/screen.xlsx'
data = pd.read_excel(local,index_col='index',sheet_name='Sheet1')
print(data) #according to index number
condition1 ="gender == 'M' and total >= 150"
print(data.query(condition1))
"""
  name gender  birthdata  subject1  subject2  subject3  total    address
index                                                                       
1        A      M 1983-01-05        64        49        49    162   shanghai
2        B      F 1983-10-27        61        61        60    182    beijing
3        C      F 1994-01-07        58        49        33    140     wuhuan
4        D      F 1987-02-06        69        44        58    171  guangzhou
5        E      M 1989-07-08        37        63        42    142      henan
      name gender  birthdata  subject1  subject2  subject3  total   address
index                                                                      
1        A      M 1983-01-05        64        49        49    162  shanghai

"""
```

### TEXT SCREENING

.str.startswith('a')

.str.endwith('b')

.str.contians(pat,case=True,flags=0,na=nan,regex=True)

* pat: string/regular expression

### Date Screening

```python
import pandas as pd
local = 'C:/pandas/screen.xlsx'
data = pd.read_excel(local,index_col='birthdata',parse_dates=['birthdata'])
print(data['1989'])
```

data2 = data.sort_values('birthdata')

print(data2.turncate(before='1980'))

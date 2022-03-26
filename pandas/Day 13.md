# Day 13

## .merge()

```python
import pandas as pd
import numpy as np
data1 = pd.DataFrame({'name':['lxy','lxy','myg','lxy'],'streak1':np.array(4)})
data2 = pd. DataFrame({'name':['Jamie','lxy','Una','Jamie'],'streak2':np.array(4)})
data3 = pd.merge(data1,data2)
print(data3)
pd.merge(data1,data2,on='name',how='inner') #inner join ,left join, right join
pd.merge(left,right,on=['key1','key2'])
```

# Concat

```python
import pandas as pd
import numpy as np
arr = np.arange(9).reshape((3,3))
arr1 = np.concatenate([arr,arr],axis=1)
arr2 = np.concatenate([arr,arr],axis=0)
print(arr1)

pd.concat([d1,d2,d3],key=['a','b','c'])
```



## Autofill

The data begin not from top of corner:

```python
import pandas as pd

local = 'C:/pandas/autofill.xlsx'
data = pd.read_excel(local,skiprows=8,usecols='F:I')
print(data)
'''
   index   name  gender  date
0    NaN  Jamie     NaN   NaN
1    NaN  Jason     NaN   NaN
2    NaN    Una     NaN   NaN
'''

import pandas as pd

local = 'C:/pandas/autofill.xlsx'
data = pd.read_excel(local,skiprows=8,usecols='F:I',dtype={'index':str})
for i in data.index:
    data['index'].at[i] =i + 1
    data['gender'].at[i] = 'male' if i%2 ==0 else "female"
print(data)
'''
  index   name  gender  date
0     1  Jamie    male   NaN
1     2  Jason  female   NaN
2     3    Una    male   NaN
'''
```

table should be float rather than integrate 

you can change the index row's type (dtype={'index':str}))

### datetime model 

~~~python
import pandas as pd
import datetime as dt
local = 'C:/pandas/autofill.xlsx'
data = pd.read_excel(local,skiprows=8,usecols='F:I',dtype={'index':str})
start_date = dt.date(2022,3,26)
for i in data.index:
    data['index'].at[i] =i + 1
    data['gender'].at[i] = 'male' if i%2 ==0 else "female"
    #data['date'].at[i] = start_date + dt.timedelta(days=i) 
    data['date'].at[i] = dt.date(start_date.year+i,start_date.month,start_date.day)
print(data)
```
  index   name  gender        date
0     1  Jamie    male  2022-03-26
1     2  Jason  female  2022-03-27
2     3    Una    male  2022-03-28
```
data.set_index('index',inplace=True)
data.to_excel(local)
~~~

### **Algorithm** (datetime)

```python
import datetime
def sum_month(date,import_month):
     year = import_month // 12
     month = date.month + import_month % 12
     if month != 12:
          year = year + month//12
          month = month%12
     return datetime.date(date.year+year,month,date.day)

```
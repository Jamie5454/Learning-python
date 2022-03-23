# Day 10

## Base Indexing and Slicing

```PYTHON
import numpy as np
a = np.arange(10)
print(a[3:9])
A = np.arange(20).reshape(4,5)
print(A[0,1])
PRINT(A[0:1,1:2])
```

For 2 dimension： A[ROW,COLUNM]



## Bool indexing

```python
import numpy as np
a = np.arange(10).reshape(5,2)
b = a>5
print(b)
[[False False]
 [False False]
 [False False]
 [ True  True]
 [ True  True]]
--------------------------------------------------------------------
import numpy as np
a = np.arange(10)
a[a<=5]=1
a[a>5]=0
print(a)
#[1 1 1 1 1 1 0 0 0 0]

import numpy as np
a = np.arange(1,21).reshape(4,5)
select = a[:,3]>5
a[:,3][select]=520
print(a)
---------------------------------------------------------------------
import numpy as np
a =np.arange(10)
condition =((a%2==0)|(a<7))
print(a[condition])
#[0 1 2 3 4 5 6 8]
```

## another type of indexing

#### for one dimension

```PYTHON
import numpy as np
a = np.array([5,3,1])
print(a[[2,1,0]]) #[1 3 5]
```

#### for two dimension

represent the row num from 0~n-1 column from 0~n-1 **[[row],[column]]**

```python
import numpy as np
a = np.arange(20).reshape(4,5)
print(a)
print("="*30)
print(a[[2,1,0]])
[[ 0  1  2  3  4]
 [ 5  6  7  8  9]
 [10 11 12 13 14]
 [15 16 17 18 19]]
==============================
[[10 11 12 13 14]
 [ 5  6  7  8  9]
 [ 0  1  2  3  4]]
```

argsort() use for reorder array

==.transpose()==

```python
import numpy as np
a = np.arange(20).reshape(4,5)
print(a.transpose())
```

## Axis

shape(4,3,2)   axis(0,1,2 )

==.swapaxes(1,0)==

```python
import numpy as np
a = np.arange(20).reshape(4,5)
print(a.swapaxes(1,0))
```
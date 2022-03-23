# Day 11

## Numpy function

* np.exp()

* np.sqrt()

* np.maxmium()

* np.minmium()

  ```
  import numpy as np
  a = np.arange(10)
  print(np.sqrt(a))
  ```

## Math and Statistic method

```python
import numpy
import numpy as np
a = np.arange(10)
print(f'{a}')# [0 1 2 3 4 5 6 7 8 9]
print(np.sum(a))#45
print(np.cumsum(a))#[ 0  1  3  6 10 15 21 28 36 45]
print(np.max(a))#9
print(np.min(a))#0
print(np.argmax(a))#9 the location of max
print(np.argmin(a)#0
np.mean() np.median() numpy.average()
```

## condition

```python
import numpy as np
a = np.array([[1,3,6],[9,3,2],[1,4,3]])
print(a)
print(f'array：{a}')
print('='*30)
print(a>3)
print(np.where(a>3,520,1314))
==============================
[[False False  True]
 [ True False False]
 [False  True False]]
[[1314 1314  520]
 [ 520 1314 1314]
 [1314  520 1314]]
```

## Sum&Any&all&Sort

```python
import numpy as np
a = np.array([[1,3,6],[9,3,2],[1,4,3]])
print((a>3).sum())

import numpy as np
a = np.array([True,False,True])
print(a.any()) #true
print(all(a)) #false
```

The different between a.sort() with sort(a)

```python
import numpy as np
a = np.array([3,6,7,9,2,1,8,5,4])
np.sort(a) 
print(a)  #[3,6,7,9,2,1,8,5,4]

------------------------------------------
import numpy as np
a = np.array([3,6,7,9,2,1,8,5,4])
a.sort()
print(a) #[1 2 3 4 5 6 7 8 9]

```

Two dimension #axis (0,1)     

```python
import numpy as np
a = np.array([[0,12,48],[4,18,14],[7,1,99]])
print(np.sort(a))
print(np.sort(a,axis=0)
#[[ 0 12 48]
 [ 4 14 18]
 [ 1  7 99]]
[[ 0  1 14]
 [ 4 12 48]
 [ 7 18 99]]
```

## Argsort

```python
import numpy as np
a = np.array([12,48,0])
print(np.argsort(a)) #[2 0 1]
print(np.argsort(-a)) #[1 0 2]
```

## Unique&in1d

```python
import numpy as np
a = np.array([12,48,0,0])
print(np.unique(a))  #[ 0 12 48]
print(np.in1d(a,[12,0,2])) #[ True False  True  True]

```

# Different copy

```python
a=b[:]  #b change with a change
a=b.copy() # b is an independent array
```
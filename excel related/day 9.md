# day 9

## Numpy

### why use numpy?  

```python
def array_sum(n):
    a = [i**3 for i in range(1,n+1)]
    b = [i**2 for i in range(1,n+1)]
    c = []
    for i in range(n):
        c.append(a[i]+b[i])
    return c

print(array_sum(3))
print(range(1))

import numpy as np
def array_sum(n):
    a = np.arange(1,n+1)**3
    b = np.arange(1,n+1)**2
    return a+b
print(array_sum(3))
```

### Three way of creating array:

```python
import numpy as np
a = np.array([1,2,3,4,5])  #do not use this one too complicatied 
b = np.array(range(1,6))
c = np.arange(1,6)
print(a,b,c)
```

### change type

```python
import numpy as np
a = np.array([1,2,3,4,5],dtype=float)

print(a.dtype)
```

## Properties of array

* **shape**: return a array, represent arrays' dimension   ==(5,)== one dimension, 5 numbers inside
* **ndim**: return a number ==1==
* **size**: return numbers inside ==5==  (total numbers)
* **dtype**: return type ==int32==



### Different way to create array:

#### Equivariant arrays

```python
import numpy as np
a = np.array(range(1,10,2))
print(a)  #[1 3 5 7 9]

import numpy as np
a = np.arange(1,10,2)
print(a)  #[1 3 5 7 9]
```

#### both 1 array & 0 array & same number array

~~~python
import numpy as np
a = np.ones(3,dtype=int)
print(a)  #[1 1 1]


import numpy as np
a = np.ones((3,3))
print(a)
```
[[1. 1. 1.]
 [1. 1. 1.]
 [1. 1. 1.]]
```

import numpy as np
a = np.full((3,3),520)
print(a)
~~~

## Multi dimension array:

```
import numpy as np
a = np.ones((3,3,3))
print(a)
```

### function: np.ones_like

transfer the original one to all one arrays which are same shape

```python
import numpy as np
a = np.array([[1,2,3],[4,5,6],[7,8,9]])
b = np.ones_like(a)
print(b)
#[[1 1 1]
# [1 1 1]
#[1 1 1]]
```

## random in numpy

```python
import numpy as np
a = np.random.randn()
b = np.random.randn(3)
c = np.random.randn(3,3)
np.round(a,2) round to two Decimals
print(a,b,c)

```

### reshape a array

```python
import numpy as np
a = np.arange(10).reshape(2,5) #should be consistancy
print(a)
```

### Calculation of array

```python
import numpy as np
a = np.arange(10).reshape(2,5) #should be consistancy
b = np.random.randn(2,5)
print(a+b)
```

**Rule:** Need the same dimension and number,
But if the number is different and the dimension is the same, the smaller dimension will copy the phase
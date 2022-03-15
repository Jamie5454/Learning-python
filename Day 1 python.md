# Day 1 python

## print out contents

```python
print('Hello world')
# using ',' or space
print('Hello','world','!','Jamie')
```

## Comment my code

``` python
# this is single line

'''
#this multi-line
'''
"""
"""
```

## Variable

```python
name = 'Allen' #string use ' '
print(name)
num = 100
print(num)
```

Variable Name = Variable Value

Variable Name :

* only number, words and _

* ==first one== can't be number

* can't be defined name 

  |   and    |   as    | assert | break | class |  true  | continues |  def   |  del  | elif |  else  |
  | :------: | :-----: | :----: | :---: | :---: | :----: | :-------: | :----: | :---: | :--: | :----: |
  |  except  | finally |  for   | from  | false | global |    if     | import |  in   |  is  | lambda |
  | nonlocal |   not   |  none  |  or   | pass  | raise  |  return   |  try   | while | with | yield  |

  

* ==Different== capitalization



## Types

### number

#### ***int() : integer   float():fractional***

```python
int1 = 10
float1 = 10.5
print(int1)
print(float1)

# type() using to check type
```

### bool () : ***Ture/false***

```python
b1 = True
b2 = False
print(b1,"===",b2 )
print(type(b1),"===",type(b2))
```

### Str() : string  *using' '*

```python 
name = 'Allen' #string use ' '
```

## Store multiple data

### List[]  tuple()  set{}  dic{a1,a2}

```python
list1=[10,20,30]
tuple1=(100,200,300)
set1={101,102,103}
dict1={"name","Jamie"}
```

## Assignment Operators

### another way assignment

```python
num1,num2,num3 = 1,2,3
print(num1,num2,num3)
# right and left have same number data
a=b=100
print(a,b)
# a and b both
```

### Operators +=, -=, *=

```python
a=100
a+=10 # a= a+10
print(a)
b=300
b*=1+2 #b = b*(1+2)
```

## Comparison Operators

### *== != >= <=*

```python
a = 100
b = 200
print(a == b) #f return bool
```

## logical operators

### and or not

```python
a,b,c = 1,2,3
print(a>b and b>c)
# both true return true
print(c.b or b>a)
#either true treturn true
print(not True) #False
print(not a>b) #True
```


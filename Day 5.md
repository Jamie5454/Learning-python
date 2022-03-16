# Day 5

##  Definition

```python
def fun1():
    print('hello')

fun1()



def fun2(info1):
    print(f'hello{info1}~')
    
fun2("Jamie")



def fun3(*args):
    for i in args:
        print(i)

fun(1,2,3)
```

> *for tuple    **for diction  
>
> > using `return` saving fun's values

## class

~~~python
class person:
    def __init__(self,name:str,gender:str='male',age:int=25):
        self.name=name
        self.gender=gender
        self.age=age

    def eat(self):
        print('eatting')

    def study(self,info:str):
        print(f"working on{info}")

    def show_me(self):
        print( f'My name {self.name}, my gender is {self.gender}, my age is{self.age}' )
p1 =person('jamie')
p1.eat()
p1.study("python")
p1.show_me()
```
eatting
working onpython
My name jamie, my gender is male, my age is25
```
~~~

## import

### two way of importing

```python
import random
print(random.randint(1,100)) #1
from random import randint
print(randint(1,100))       #2
from random import randint as int
print(int(1,100))       #3
```

math time
# day 3 python

## List

### Append

append can only use to add **one** variable

```python
list=["hello","Jamie"]
print(name.append('!'))#hello,jamie,!

```

### Extend

```python
list=["hello","Jamie"]
print(list.extend['1','2'])#hello,jamie,1,2
printprint(list.extend['123'])#hello,jamie,1,2,3
```

### insert and delet

from a certain position  .insert(pos num,'content')

``` python
list=["hello","Jamie"]
print(list.insert(1,"Mr"))
#hello mR Jamie
print(del list[1]) #hello
```

### Pop

```python
list=["hello","Jamie"]
print(list.pop(0))
print(list)
#hello
['Jamie']
```

## remove & clear&reverse&sort&in

```python
list=["hello","Jamie"]
list.remove("hello")
print(list)# Jamie

list=["hello","Jamie"]
list.clear()
print(list) #[]

list=["hello","Jamie"]
list.reverse()
print(list) #Jamie，hello


list=["hello","Jamie"]
list.sort()
print(list) #Jamie，hello


list=["hello","Jamie"]

print("hello" in list) #Ture
```



## dictionary

### empty

``` python
dict1 ={}
dict1['name']="Jamie" #"name":"Jamie"
print(dic1)
dict1['name']="Una" #modify
print(dic1)
print(dic1.get("Name")) #Jamie
```

## many data

```python
dict1 ={"name":"Jamie","gender":"male"}
print(dic1.keys()) #name,gender
print(dic1.value())#Jamie,male
```




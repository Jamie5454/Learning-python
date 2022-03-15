# Day 2

### String

```python
name1 ='Allen'
name2 ="Allen"
name ='''
I am Allen
hello
'''
print(name1,name2,type(name1),type(name2))
#Allen Allen <class 'str'> <class 'str'>
print(name)
#print out multi line
```



## Input Operation

```python
name = 'Jamie'
print('My name:{}'.format(name))
print('My name:{0},{1}'.format(name,'hello'))
print('My name:{n}'.format(n=name))
print(f'My name:{name}') #common way
```

## Slicing operation

### suit for *string list tuple*

```python
info='abcdefg'
print(info[2]) #c
print(info[-1]) #g
print(info[0:2]) #ab
print(info[:2]) #from begining ignore '0'
print(info[1:]) #bcdefg
print(info[::-1]) #gfedcba

```



## ordinary methods

### search T&F modify

info.replace("chose","replace",***num***)

```python
info = "hello world and my friends and you"
print(info.find("and")) #12
print(info.find('ands')) #-1 repersent cant find
print(info.index("and")) #12
print(info.index('ands')) #wrong! repersent cant find
print(info.count("and")) #2 how many
print(info.count('ands')) #0 repersent cant find

print(info.upper(),info.lower(),info.title(),info.capitalize())
print(info.replace('and','add')) #hello world add my friends add you
print(info.replace('and','add',1))#hello world add my friends and you
print(info.split("and")) #'hello world' "my friends",'you'  

name = ["happy","everydays"]
print("-".join(name)) 
#happy-everydays
```
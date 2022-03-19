# Day 6

## How to read and write in a doc

Import ==OS==

```python
import os
print(os.getcwd()) #working address
print(os.path.abspath('Day 1.py')) #local address
print(os.path.dirname('PycharmProjects\Jamie\Day 1.py'))
print(os.path.exist('C:\Users')) 
```

```python
import os
os.makedirs("tmp")  #create folders
os.rmdir("tmp")   #remove folders
f=open('aaa.py','w')  #file name , write
f.write('hello\n')   #\n change line
f.write('123\n')
f.close()

f=open("aaa.py","a") #file name, append

with open("aaa.py","r")) as f: #another way read
    f.read()
    f.readline() #1 line
    
with open('imp.jpg','rb') as f: #pic byte
with opne('imp2.jpg','wb') as f2: #pic write
```


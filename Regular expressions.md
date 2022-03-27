# Regular expressions

A regular expression is a logical formula for manipulating strings (including ordinary characters (e.g., letters between a and z) and special characters (called "meta-characters")) by using a predefined set of specific characters, and combinations of those specific characters, to form a "regular string "This "regular string" is used to express a filtering logic for strings. A regular expression is a text pattern that describes one or more strings to be matched when searching for text.

## import RE

```python
import re
string ="a1b2c3d4"
a = re.findall('[0-9]',string) #['1', '2', '3', '4']
b = re.findall('[^0-9]',string) #['a', 'b', 'c', 'd']
c = re.findall('a[de]b')

    
```

```python
import re
string = 'xyz,xcz,xfz,xdz,xaz,xez'
a = re.findall('x[d-f]z',string) #['xfz', 'xdz', 'xez']
print(a)
```

### Extracting numbers

```
a = re.findall('\d',string)  #all number
a = re.findall('\D',string)  #all nonnumber
a = re.findall('\w',string)  #only charater number word
a = re.findall('\W',string)  #Special Symbols
a = re.findall('\s',string)  #space or \n\t
a = re.findall('\S',string)  #nonspace
```

### Quantitative words

```
string = 'Excel 1234Word23456PPT12Lr'
a = re.findall('[a-zA-z]{3,5}',string)
print(a)    #['Excel', 'Word', 'PPT']
```

For this example, it will find 5 words first (ExcelVBA )-->('Excel','VBA')

### Fuzzy queries

```python
import re
string = 'Excel 1234Word23456PPT124Lr'
a = re.findall('12*',string)  #zero or infinite 
a = re.findall('12+',string) #one or infinite
a = re.findall('12?',string) #zero or one
print(a) 
```

###  Boundaries

* '^\d{11}$'  only 11 numbers
* ^ begin
* $ end
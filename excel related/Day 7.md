# Day 7

## ==Excel==

### how to open

```python
def open():
    from openpyxl import load_workbook
    wb = load_workbook('test.xlsx')

    sh1 =wb.active
    sh2 =wb['Sheet1']

    print(sh1 == sh2 )

def get_value():
    from openpyxl import load_workbook
    wb = load_workbook('test.xlsx') #whole worksheet
    sh1 = wb['Sheet1'] #one sheet
    v1 =sh1.cell(1,1) #one cell
    
    print(v1.value) #one
    print(sh1["A2"].value)  # two
show_sheets()

def get_all_value():
    from openpyxl import load_workbook
    wb = load_workbook("test.xlsx")
    sh1 = wb["Sheet1"]
    for row in sh1.rows:
        for cell in row:
            print(cell.value)
```

## create excel

```python 
def creat_new():
    from openpyxl import Workbook
    wb =Workbook()
    sh1 = wb.active  
    sh2 = wb.create_sheet("new")
    wb.save("test2.xlsx")
```

## Set value

```python
def set_value():
    from openpyxl import Workbook
    wb = Workbook()
    sh1 = wb.active
    sh1['A1']="hello"
    wb.save("test2.xlsx")
```

## Aggregate value

```python
from openpyxl import load_workbook
wb = load_workbook("file.xlsx")
sh=wb.active

data1 = []
data2 = []

for row in sh.rows:
    num=row[3].value #begin is 0 rather than 1
    if num>= 300:
        data2.append(row)
    else:
        data1.append(row)
        
data1_sh=wb.create_sheet("condition one")
data2_sh=wb.creat_sheet("condition two")
```

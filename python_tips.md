## python tips

**tip1: insert->same index**

```python
# Note: 2:2 should be the same, or it will be replaced
num1 = [1,2,5]
num2 = num1[:]#copy num1 but didn't change the original num1
num1[2:2] = [3,4,[6],[]]#[1, 2, 3, 4, [6], [], 5]
num2[2:3] = [3,4,[6],[]]#[1, 2, 3, 4, [6], []]
print(num1)
print(num2)
```

**tip2: default input is 'str'**

```python
a = input()#23
print(type(a))#<class 'str'>
```

**tip3: x.sort()->change original& sorted(x)->don't**

```python
a = input()#1 2 4 3->str
b = [int(i) for i in a.split()]#list
c = sorted(b)
print(c)#[1, 2, 3, 4]
print(b)#[1, 2, 4, 3]
b.sort()
print(b)#[1, 2, 3, 4]
```

**tip4: extract str->list('xxx')**

```python
alist = list('abcdefghijklmnopqrstuvwxyz')#['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']
```

**tip5: list.remove()->none**

```python
print([3,4,5,6,5,4,3].remove(3))#return None, cause we know remove it
```

**tip6: blank segment without error->pass**

```python
for i in range(10):
  pass
```

**tip7: ,->space**

```python
print('acccccc','baaaaaa')# acccccc baaaaaa
```

**tip8: flask usage->page navigation**

```python
from flask import Flask
# from flask import request

app = Flask(__name__)

@app.route('/', methods=['GET', 'POST'])
def home():
    str1 ='<a style="color:green" href="./second"><h1>go to the next page</h1></a>'
    return str1

@app.route('/second', methods=['GET', 'POST'])
def home1():
    str2 = '<a style="color:red" href="/"><h1>back to normal</h1></a>'
    return str2

if __name__ == '__main__':
    app.run(host="localhost", port=8030, debug=True)
```

**tip9: Request lib->similar to JQuery->python a.py>te.csv**

```python
from requests_html import HTMLSession
session = HTMLSession()
url = 'https://catalog.oregonstate.edu/courses/cs/'
r = session.get(url)
# print(r.html.html)
elementss = r.html.find('.courseblocktitle')
print('courses OSU offered follows:')
for el in elementss:
	print(el.text)
```

**tip10: round hole->python2/3 difference, refer to [hole](https://www.runoob.com/w3cnote/python-round-func-note.html)**
```python
# Round function:
# Normally, it keeps the nearest number. e.g. round(2.67,1)#2.7, but it performs different in python2 and python3. 
# If there’re equal distance. It keeps the longer distance from 0 in python 2, eg. round(0.5)#1. 
# However, rounding is done toward the even choice in python3. e.g.round(0.5)#0, 
>>> round(2.6845,3) # 2.684
>>> round(2.6855,3) # 2.686
>>> round(123.84) # 124
>>> round(123.84,-2) # 100.0, float, not 100
>>> math.floor(15.5) # 15
>>> print(int("20",16),int("101",2)) # 32 5,Hexadecimal and binary
>>> print(hex(16),bin(10)) # 0x10 0b1010,convert to hex and binary
>>> abs(1-2j) # 2.23606797749979, it equals to sqrt(5)
```

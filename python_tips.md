## python tips

**tip1: insert->same index**

```python
# Note: 2:2 should be the same, or it will be replaced
num1 = [1,2,5]
num2 = num1[:] # copy num1 but didn't change the original num1
num1[2:2] = [3,4,[6],[]]#[1, 2, 3, 4, [6], [], 5]
num2[2:3] = [3,4,[6],[]]#[1, 2, 3, 4, [6], []]
print(num1)
print(num2)
```

**tip2: print format**

```python
>>> '{0:*^10}'.format(100) # '***100****'
>>> '{0:*>10}'.format(100) # '*******100’
>>> '{0:*<10}'.format(100) # '100*******’
>>> '{:.2f}'.format(1/3) # ‘0.33',notice the :
a = input() # 23
print(type(a)) # <class 'str'>, default input is 'str'
print('acccccc','baaaaaa')# ','->space**, result: acccccc baaaaaa
```

**tip3: multiple command end: double return**

**tip4: flask usage->page navigation**

```python
from flask import Flask
# from flask import request

app = Flask(__name__)

@app.route('/', methods=['GET', 'POST'])
def home():
    str1 ='<a style="color:green" href="./second">\
    <h1>go to the next page</h1></a>'
    return str1

@app.route('/second', methods=['GET', 'POST'])
def home1():
    str2 = '<a style="color:red" href="/">\
    <h1>back to normal</h1></a>'
    return str2

if __name__ == '__main__':
    app.run(host="localhost", port=8000, debug=True)
```

**tip5: list.remove()->none**

```python
print([3,4,5,6,5,4,3].remove(3)) #return None, since we know remove it
```

**tip6: Request lib->similar to JQuery->python a.py>te.csv**

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

**tip7: round function perform differently in python2/3, refer to [hole](https://www.runoob.com/w3cnote/python-round-func-note.html)**

```python
# Round function:
# Normally, it keeps the nearest number. e.g. round(2.67,1) #2.7
# However, it performs different in py2 and py3 when equal distance
# It keeps the longer distance from 0 in py2, eg. round(0.5) #1, 
# but rounding is done toward the even choice in py3. e.g.round(0.5) #0 
>>> round(2.6845,3) # 2.684
>>> round(2.6855,3) # 2.686
>>> round(123.84) # 124
>>> round(123.84,-2) # 100.0, float, not 100
>>> math.floor(15.5) # 15
>>> print(int("20",16),int("101",2)) # 32 5,Hexadecimal and binary
>>> print(hex(16),bin(10)) # 0x10 0b1010,convert to hex and binary
>>> abs(1-2j) # 2.23606797749979, it equals to sqrt(5)
```
**tip8: [increase recursion maximum](https://stackoverflow.com/questions/3323001/what-is-the-maximum-recursion-depth-in-python-and-how-to-increase-it) and ['setup' segment](https://docs.python.org/3/library/timeit.html)**

```python
import sys
import timeit
# maximum increase
print(sys.getrecursionlimit())
sys.setrecursionlimit(1500)
# segment setup
timeit.timeit(stmt="fibi(10)", setup="from tstt import fibi", number = 30)
```

**tip9: @staticmethod->build-in method**

There's also a default [self] parameter (https://stackoverflow.com/questions/23944657/typeerror-method-takes-1-positional-argument-but-2-were-given) in each class function

**tip11: dataType and operations**

datatype->int, float, bool, str, list, tuple, set, dict

print(5/2) #2.5->important!

print(5//2) #2


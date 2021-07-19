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

**tip3: x.sort()->change original & sorted(x)->don't**

```python
a = input()#1 2 4 3->str
b = [int(i) for i in a.split()]#list
c = sorted(b)
print(c) # [1, 2, 3, 4]
print(b) # [1, 2, 4, 3]
b.sort()
print(b) # [1, 2, 3, 4]
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

**tip7: multiple command end: double return**

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

**tip10: round function perform differently in python2/3, refer to [hole](https://www.runoob.com/w3cnote/python-round-func-note.html)**

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
**tip11: useful knowledge from <<Python程序设计(陈春晖)>>**

1. Python3中的 字符串是 Unicode字符串而不是字节数组,这是与 Python2的主要差别之一。

2. “.”表示当前路径,在通常情况下可以省略,只有在特殊情况下才不能省略。
e.g. .\system32\cmd.exe

3. 从软件工程角 度来看,只有在高级语言不能满足设计要求,或不具备支持某种特定功能的技术性能 (如特殊的输入输出)时,汇编语言才被使用。

4. 3个十分经典的科学计算扩展 库:NumPy、Pandas和 Matplotlib,它们分别为Python语言提供了快速数组处理、数值运算 以及绘图功能。

5. python不支持的数据类型是char 、byte类型。Python没有char或byte类型来保存单一字符或 8 比特整数。你可以使用长度为 1 的字符串表示字符或 8 比特整数。
python的数据类型有：数字(int)、浮点(float)、字符串(str)，列表(list)、元组(tuple)、字典(dict)、集合(set)

6. C语言中字符串使用'\0'作为结束符，以防止越界。但是在python中，不是, 不需要为是否已经添加终止符而担心。字符串值包含你所定义的东西，没别的。


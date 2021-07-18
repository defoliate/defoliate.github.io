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

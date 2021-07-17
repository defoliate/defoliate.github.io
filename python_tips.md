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

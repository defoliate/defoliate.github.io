## programming exercise

**ex1: generate random 8 passcode**

```python
import random
a1 = [chr(i) for i in range(65,91)] # capital A-Z
a2 = [chr(i) for i in range(97,123)] # a - z
a3 = [str(i) for i in range(0,10)] # 0-9
a = a1 + a2 + a3
random.shuffle(a)
b = random.sample(a,8)
c = ''.join(b)
print(c)
```

**ex2: binary search, refer to [binary search](https://www.geeksforgeeks.org/binary-search/)**

```python
def bSearch(arr, left, right, x):
  times = 0
  while left <= right:
    times += 1
    mid = (left + right) // 2
    if x < arr[mid]:
      right = mid -1
    elif x >arr [mid]:
      left = mid +1
    else: # x == a[mid]
      print('find it, the position is in {0},times={1}'.format(mid,times))
      break # end key
  # element doesn't exist ->end it
  else:
    print('the element is not exist.')

a = [1,2,3,4,5,8] 
bSearch(a, 0, len(a)-1, 4)#times: 8->3,3->1,4->3
```

**ex3: decorator usage: pass a whole function object, refer to [args](https://www.geeksforgeeks.org/args-kwargs-python/) and [decorator](https://www.geeksforgeeks.org/decorators-in-python/)**

```python
def decorator(func):
  # *args stands for varible parameter without keywords
  # **kwargs stands for varible parameters with keywords
  def partial_func(*args,**kwargs):    
    print('func={0}:args={1},kwargs={2}'.format(func.__name__,args,kwargs))
    func(*args,**kwargs)
  return partial_func

@decorator
def some_func():
  return print('someeee')

@decorator
def any_func(*args,**kwargs):
  return print("anyyyy")

# return the execute result
# case1: no para
# func=some_func:args=(),kwargs={}
# someeee
some_func()
# equivalent
decorator(some_func())

# case 2: has paras. 
# func=any_func:args=('aaa', 'bbb'),kwargs={'key1': 'ccc', 'key2': 'ddd'}
# anyyyy
any_func('aaa','bbb',key1='ccc',key2='ddd')

# 'function' itself is a type
print('=====')
print(type(any_func)) # class 'function'
print('~~~~~~')
print(decorator(any_func())) # return the execute result + a 'function'
```

**ex4: fib->recursive+dic, refer to [recursive function](https://www.python-course.eu/python3_recursive_functions.php)**

```python
# ordinary method: recursive, lowest
def fib(n):
  if n == 0 or n == 1:
    return n
  else:
    return fib(n - 1) + fib(n - 2)

# memorize the previous result by dict->linear, fastest
def fibm(n):
  memo = {0:0, 1:1}
  if n not in memo:
    memo[n] = fibm(n - 1) + fibm(n - 2)
  return memo[n]

# keep the latest only ->linear search, faster
def fibi(n):
  if n == 0:
    return 0
  old, new = 0, 1
  for i in range(n-1):
    old, new = new, old + new
  return new

print([fibi(i) for i in range(10)])
print('fib = {0}, fibm = {1}, fibi = {2} '.format(fib(10),fibm(10),fibi(10)))
```

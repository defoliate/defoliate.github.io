## programming exercise

**ex1: generate random 8 passcode**

```python
import random
a = [chr(i) for i in range(65,91)] + [chr(i) for i in range(97,123)] + [str(i) for i in range(0,10)]
random.shuffle(a)
b = random.sample(a,8)
c = ''.join(b)
print(c)
```

**ex2: binary search**

```python
a = [1,2,3,4,5,8] 
def search(x):
  left = 0
  right = len(a) - 1
  times = 0
  # if the element doesn't exist,end it. if always 'True'->search forever 
  while left <= right:
    times += 1
    mid = (left + right) // 2
    if x < a[mid]:
      right = mid -1
    elif x >a [mid]:
      left = mid +1
    else: # x == a[mid]
      print('find it, the position is in {0},times={1}'.format(mid,times))
      break # end key
  else:
    print('the element is not exist.')
search(4) # times: 8->3,3->1,4->3
```

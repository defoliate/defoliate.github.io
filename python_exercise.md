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

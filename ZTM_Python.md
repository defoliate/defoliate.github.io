## Python basics

**why so many programming languages?**

different usage, it also involves.

**format and str->immutable**

```python
 # f->format the content
name = "John"
age = 55
print(f"my name is {name} and I'm  {age} years old.")

#string is immutable
a="to be is not to be"
b=a.replace("be","me")
print(b)
print(a)
```
**comment only when necessary**

**list->order, can be change; dict->random, key is immutable; string/int->can't be changed**

```Python
# TypeError: unhashable type: 'list'
my_list = [
  {
  "a" : [1,2,3],
  123:"bb",
  True:2,
  [1,2]:True
}
]
print(my_list[0][0])

# ======
# overwrite->hell
my_list = [
  {
  "a" : [1,2,3],
  "a":"hell"
}
]
print(my_list[0]["a"])

# ======
# set default if none
user = {
  "basket" : [1,2,3],
  "greet":"hello",
  "c":12
}
print(user.get("c","a"))

# ======
# single comma in tuple
tuplea = (1,2,3)
print(tuplea[1:2])
print(tuplea[1:3])
# no comma in list
l = [1,2,3]
print(l[1:2])
print(l[1:3])
```
## Python basics 2

```python
# compare == and is
a = [1,2,3]
b = [1,2,3]
print(a == b) # True,check value
print(a is b) # False, check exact memory


# search duplicate elements
some_list = ['a','b','c','b','d','m','n','n']
duplicate = []
for items in some_list:
  if some_list.count(items) > 1:
    if items not in duplicate:
      duplicate.append(items)
print(duplicate)
```

### Python Lists

Lists are flexible aggregate data structures, capable of holding onto a huge amount of serial and nested data and manipulate it quicky.

Create a list
```python
list = ['strawberry','blueberry','blackberry']
```

Add to the end of a list
```python
list = ['strawberry','blueberry','blackberry']
list.append('cloudberry')
#results in ['strawberry', 'blueberry', 'blackberry', 'cloudberry']
```

Delete all items from list
```python
list = ['strawberry','blueberry','blackberry']
list.clear()
#results in []
```

Get length of list
```python
list = ['strawberry','blueberry','blackberry']
length = len(list)
#results in length = 3
```

Get specific item in list based on position (0-indexed)
```python
list = ['strawberry','blueberry','blackberry']
berry = list[1]
#results in berry = blueberry
```

Insert item into list at position (0-indexed)
```python
list = ['strawberry','blueberry','blackberry']
list.insert(0,'boisinberry')
#results in ['boisinberry','strawberry','blueberry','blackberry']
list.insert(2,'loganberry')
#results in ['boisinberry','strawberry','loganberry','blueberry','blackberry']
```

Remove item from list at position (0-indexed)
```python
list = ['strawberry','blueberry','blackberry']
list.pop(1)
#results in ['strawberry','blackberry']
```

Remove specific item in list (0-indexed)
```python
list = ['strawberry','blueberry','blackberry']
list.remove('blueberry')
#results in ['strawberry','blackberry']
```

Find item index in list (0-indexed)
```python
list = ['strawberry','blueberry','blackberry']
bluePos = list.index('blueberry')
#results in bluePos = 1
```

Sort a list numerically *or* alphabetically
```python
list = ['strawberry','blueberry','blackberry']
list.sort()
#results in ['blackberry', 'blueberry', 'strawberry']
```

Reverse a list
```python
list = ['strawberry','blueberry','blackberry']
list.reverse()
#results in ['blackberry', 'blueberry', 'strawberry']
```

Copy a list
```python
list = ['strawberry','blueberry','blackberry']
revList = list.copy()
revlist.reverse()
#results in 2 lists, 1 of them flipped
```

Count item in list
```python
list = ['strawberry','blueberry','blueberry','blackberry']
blueCount = list.count('blueberry')
#results in blueCount = 2
```

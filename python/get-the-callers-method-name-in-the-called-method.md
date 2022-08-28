```python
>>> import inspect
>>> def f1(): f2()
...
>>> def f2():
...   curframe = inspect.currentframe()
...   calframe = inspect.getouterframes(curframe, 2)
...   print('caller name:', calframe[1][3])
...
>>> f1()
caller name: f1
```

[Source](https://stackoverflow.com/a/2654130)

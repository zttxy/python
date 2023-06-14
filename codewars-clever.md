
## Who likes it?

```python
def likes(names):
    n = len(names)
    return {
        0: 'no one likes this',
        1: '{} likes this', 
        2: '{} and {} like this', 
        3: '{}, {} and {} like this', 
        4: '{}, {} and {others} others like this'
    }[min(4, n)].format(*names[:3], others=n-2)
```
解释：
1. 以`[min(4, n)]`为键对字典取值，得到字符串
2. 对字符串格式化处理：在`format`函数中传入可变参数`*names`，并对其切片，将切片后的元素依次传入`{}`
3. `*names`表示把`names`这个list的所有元素作为可变参数传进去。这种写法相当有用，而且很常见。若不加*，则是将整个列表传入第一个`{}`。
> ```python
> # 可见如下区分
> p = ['Alex', 'Jacob', 'Mark', 'Max']
> >>>print(p[:3])
> ['Alex', 'Jacob', 'Mark']
> >>>print(*p[:3])
> Alex Jacob Mark
> ```

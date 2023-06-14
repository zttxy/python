
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
1. 没有用传统的多重条件判断，而是以`[min(4, n)]`为键对字典取值，得到字符串.
2. 对字符串格式化处理：在`format`函数中传入可变参数`*names`，并对其切片，将切片后的元素依次传入`{}`.
3. `*names`表示把`names`这个list的所有元素作为可变参数传进去，这种写法相当有用，而且很常见.
> ```python
> # 若不加 * ，则是将整个列表传入第一个 {} 。可见如下区分
> p = ['Alex', 'Jacob', 'Mark', 'Max']
> >>> print(p[:3])
> ['Alex', 'Jacob', 'Mark']
> >>> print(*p[:3])
> Alex Jacob Mark
> >>> '{}, {}'.format(p[:3])
> IndexError: Replacement index 1 out of range for positional args tuple  # 由于第一个括号（索引为0）内传入了整个切片列表，第二个括号（索引为1）缺少可传值，出现报错
> >>> '{}, {}'.format(*p[:3])
> 'Alex, Jacob'  # 有几个括号就按顺序传入前几个元素，多余的元素不会传入
> ```
4. 在此复习`f-string`语法
> ```python
> # f-string 格式化字符串以 f 开头，后面跟着字符串，字符串中的表达式用大括号 {} 包起来，它会将变量或表达式计算后的值替换进去
> >>> name = 'Runoob'
> >>> f'Hello {name}'
> 'Hello Runoob'  # 将变量替换为值
> ```

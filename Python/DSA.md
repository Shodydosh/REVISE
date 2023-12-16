## Tháp Hà Nội
### `st -> au, au -> end`
```python
def move(n, st, au, end):
    if (n == 1):
        print(st + " -> " + end)
        return
    move(n-1, st, end, au)
    print(st + " -> " + end)
    move(n-1, au, st, end)


A, B, C = 'A', 'B', 'C'
move(int(input()), A, B, C)

```
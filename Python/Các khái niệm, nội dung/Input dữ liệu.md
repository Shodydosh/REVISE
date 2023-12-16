n, k = list(map(int, input().split()))
nums = list(map(int, input().split()))

## Nhập matrix

```python
matrix = []
m, n = list(map(int, input().split()))
for i in range(m):
    row = list(map(int, input().split()))
    matrix.append(row)
replace_prime_numbers(matrix)
```

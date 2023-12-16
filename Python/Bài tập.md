### Dãy con ngắn nhất
- Thuật toán:
  *Cho dãy số A[] có N phần tử. Nhiệm vụ của bạn là tìm dãy con liên tiếp có độ dài nhỏ nhất, sao cho Ước số chung lớn nhất của tất cả các phần tử trong dãy đúng bằng K.*
```python
import math
from sys import *

v = []
for line in stdin:
    v += list(map(int, line.split()))
t = v[0]
pos = 1
while t > 0:
    n, k = v[pos], v[pos+1]
    pos += 2
    a = v[pos: pos + n]
    pos += n
    minLen = 10 ** 10
    for i in range(n):
        gcd = a[i]
        curLen = 0
        for j in range(i, n):
            gcd = math.gcd(gcd, a[j])
            if (gcd == k):
                curLen = j - i + 1
                minLen = min(curLen, minLen)
                break
    if (minLen == 10 ** 10):
        print(-1)
    else:
        print(minLen)
    t -= 1
```

### Chuyển đổi nhị phân sang 2, 4, 8, 16
- Đọc file DATA.in
```python
import math


def convert(a):
    n, b = 0, 1
    for i in range(len(a) - 1, -1, -1):
        n += int(a[i]) * b
        b *= 2
    if n < 10:
        return n
    return chr(65 + n % 10)


# f = open('C:\\Users\\ADMIN\\Tung\\Code\\Python\\DATA.in')
f = open('DATA.in')
t = int(f.readline())
while (t > 0):
    b = int(f.readline())
    b = int(math.log2(b))
    s = f.readline().strip()
    while len(s) % b != 0:
        s = '0' + s
    for i in range(0, len(s), b):
        print(convert(s[i:i+b]), end='')
    print()
    t -= 1

```

### Số đặc biệt
```python
def solve():
    n, k = map(int, input().split())
    mod = int(1e9) + 7
    ans = 0
    tmp = 1
    while k > 0:
        if k % 2 == 1:
            ans = (ans + tmp) % mod
        tmp *= n
        k //= 2
    print(ans)


t = int(input())
while t > 0:
    solve()
    t -= 1
```

## Nguyên tố cùng nhau
- `math.gcd`, lũy thừa
```python
import math
n, k = [int(x) for x in input().split()]
cnt = 0
for x in range(10**(k-1), 10**k):
    if (math.gcd(x, n) == 1):
        cnt += 1
        print(x, end=" ")
    if cnt == 10:
        cnt = 0
        print()
```

## Ký tự thứ K
- Chia để trị, cắt đôi, `ord(char)` để lấy giá trị int của char
```python
import math
def solve(n, k):
    if (k == 2 ** (n-1)):
        return n  # middle
    if (k > 2 ** (n-1)):
        return solve(n-1, k-2**(n-1))  # right part
    else:
        return solve(n-1, k)  # left part
for _ in range(int(input())):
    n, k = map(int, input().split())
    print(chr(solve(n, k) + ord('A') - 1))
```

## Tách đôi và tính tổng(big int)
```python
s = input()
while (len(s) > 1):
    tmp = len(s)//2
    tmp2 = int(s[:tmp]) + int(s[tmp:])
    print(tmp2)
    s = str(tmp2)
```

## Phân chia nguyên tố
```python
import math
def check(n):
    if n < 2:
        return False
    for i in range(2, int(math.sqrt(n))+1):
        if n % i == 0:
            return False
    return True
n = int(input())
a = list(map(int, input().split()))
b = []
sum = 0
for x in a:
    if x not in b:
        sum += x
        b.append(x)
curSum = 0
chk = True
for i in range(0, len(b)):
    curSum += b[i]
    if check(curSum) and check(sum-curSum):
        print(i)
        chk = False
        break
if chk:
    print("NOT FOUND")
```
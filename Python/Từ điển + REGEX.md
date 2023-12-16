## THỐNG KÊ TỪ KHÁC NHAU

```python
import re
t = int(input())
res = []
for _ in range(t):
    s = input().lower()
    res += re.findall(r'\b\w+\b', s) 
    #Tìm tất cả các từ, không lẫn với kí tự .,/!;:?
dict = {}
for w in res:
    if w not in dict: dict[w] = 1
    else: dict[w] += 1
freq = []
for z in dict:
    freq.append({"w": z, "f": dict[z]})
freq.sort(key=lambda x: (-x['f'], x['w']))

for z in freq:
    print(f"{z['w']} {z['f']}")
```
```python
import re
a = {}
for _ in range(int(input())):
    for s in re.split("[^a-z0-9]", input().lower()):
        if (s != ''):
            if s not in a:
                a[s] = 1
            else:
                a[s] += 1
res = sorted(a, key=lambda x: (-a[x], x))
for i in res:
    print(i, a[i])
```

## Đỉnh thắt

```python
adj = [0] * 1001
visited = [False] * 1001
def dfs(i):
    visited[i] = True
    for j in adj[i]:
        if not visited[j]:
            dfs(j)
def memset():
    for i in range(1001):
        adj[i] = list()
for _ in range(int(input())):
    memset()
    cnt = 0
    n, m, s, t = [int(x) for x in input().split()]
    for _ in range(m):
        z1, z2 = [int(x) for x in input().split()]
        adj[z1].append(z2)
    for point in range(1, n+1):
        if point != s and point != t:
            visited = [False] * 1001
            visited[point] = True
            dfs(s)
            if not visited[t]:
                cnt += 1
    print(cnt)
```

## DS môn thi

```python
ds = []
for _ in range(int(input())):
    id = input()
    name = input()
    ht = input()
    ds.append({'id': id, 'name': name, 'ht': ht})
ds.sort(key=lambda x: x['id'])
for x in ds:
    print(f"{x['id']} {x['name']} {x['ht']}")
```

## Loại bỏ số nguyên

```python
import sys

def check(s):
    k = 0
    for i in s:
        if not i.isdigit():
            return True
        k = k * 10 + int(i)
    if k <= sys.maxsize and k >= -sys.maxsize:
        return False
    return True

file = open('DATA.in', 'r')
a = []
for line in file:
    for word in line.split():
        if check(word):
            a.append(word)
a.sort()
for i in a:
    print(i, end=' ')
```

## Chia cắt đồ thị (bỏ một đỉnh sao cho thành nhiều tplt nhất)
### - `Nhớ cho mỗi phần tử trong dict thành 1 list`
```python
def dfs(u):
    vst[u] = True
    for v in adj[u]:
        if not vst[v]:
            dfs(v)

for _ in range(int(input())):
    adj = {}
    n, m = map(int, input().split())
    for i in range(n+1):
        adj[i] = []
    for i in range(m):
        x, y = map(int, input().split())
        adj[x].append(y)
        adj[y].append(x)

    vst = [False] * (n + 1)
    tplt = 0
    for i in range(1, n + 1):
        if not vst[i]:
            tplt += 1
            dfs(i)

    maxlt = tplt
    ans = 0
    for i in range(1, n + 1):
        vst = [False] * (n + 1)
        vst[i] = True
        tmp = 0
        for j in range(1, n + 1):
            if not vst[j]:
                tmp += 1
                dfs(j)
        if tmp > maxlt:
            maxlt = tmp
            ans = i

    print(ans)

```
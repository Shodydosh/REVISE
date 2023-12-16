```python
def check(s):
    if len(s) % 2 == 0:
        return 0
    for i in range(2, len(s), 2):
        if s[i] != s[i - 2]:
            return 0
    if (s[0] == s[1]):
        return 0
    return 1


t = int(input())
for _ in range(t):
    s = input()
    if (check(s)):
        print("YES")
    else:
        print("NO")

```


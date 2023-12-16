## Tính toán thời gian
- `sort(key = lambda x : (x.hour, x.minute), reverse = True)`
```python
class player:
    def __init__(self, a, b, c, d):
        self.id = a
        self.name = b
        self.vao = c
        self.ra = d
        hv, pv = self.vao.split(":")
        hr, pr = self.ra.split(":")
        tmp = (int(hr) * 60 + int(pr)) - (int(hv) * 60 + int(pv))
        self.hour = tmp // 60
        self.minute = tmp - self.hour * 60

    def getTime(self):
        return str(self.hour) + " gio " + str(self.minute) + " phut"

    def __str__(self):
        return self.id + ' ' + self.name + ' ' + self.getTime()


t = int(input())
ps = []
for _ in range(t):
    p = player(input(), input(), input(), input())
    ps.append(p)
ps.sort(key=lambda x: (x.hour, x.minute), reverse=True)
for p in ps:
    print(p)

```

## Lập hóa đơn 2
- datetime, datetime.strptime, strip()
```python
from datetime import datetime
tg = [0, 25, 34, 50, 80]

class Ctm:
    def __init__(self, id, name, phong, ngayDen, ngayDi, extra):
        if id >= 10:
            self.id = "KH" + str(id)
        else:
            self.id = "KH0" + str(id)

        self.name = name.strip()
        self.phong = phong.strip()
        self.extra = extra
        # Strip leading/trailing whitespaces from date inputs
        ngayDen = ngayDen.strip()
        ngayDi = ngayDi.strip()
        self.stay = (datetime.strptime(ngayDi, '%d/%m/%Y') -
                     datetime.strptime(ngayDen, '%d/%m/%Y')).days + 1
        self.tong = tg[int(self.phong[0])] * self.stay + self.extra

    def __str__(self):
        return f"{self.id} {self.name} {self.phong} {self.stay} {self.tong}"

t = int(input())
a = []
for i in range(t):
    a.append(Ctm(i + 1, input(), input(), input(), input(), int(input())))

a.sort(key=lambda x: x.tong, reverse=True)
for c in a:
    print(c)

```

## Tính vận tốc
- `FORMAT`
```python

def getId(city, name):
    cs = city.split()
    ns = name.split()
    res = ""
    for c in cs:
        res += c[0]
    for c in ns:
        res += c[0]
    return res.upper()


class person:
    def __init__(self, name, city, time):
        self.name = name
        self.city = city
        self.id = getId(city, name)
        h, m = time.split(":")
        tmp = int(h) + int(m)/60 - 6
        self.speed = 120 / tmp

    def __str__(self):
        return f"{self.id} {self.name} {self.city} " + "{:.0f}".format(self.speed) + " Km/h"


t = int(input())
ps = []
for _ in range(t):
    ps.append(person(input(), input(), input()))
ps.sort(key=lambda x: x.speed, reverse=True)
for p in ps:
    print(p)
```

## ĐIỂM TUYỂN SINH
### `' '.join(w.strip().title() for w in s.split())`
### `"{:.1f}".format(self.diem)`
```python
def fix(s):
    return ' '.join(w.strip().title() for w in s.split())
def getkv(kv):
    if kv == 1:
        return 1.5
    if kv == 2:
        return 1
    return 0
def getdt(dt):
    if dt == "Kinh":
        return 0
    return 1.5
class thiSinh:
    def __init__(self, stt, ten, diem, dantoc, kv):
        self.mts = "TS0" + str(stt)
        if (stt >= 10):
            self.mts = "TS" + str(stt)
        self.ten = fix(ten)
        self.diem = diem + getdt(dantoc) + getkv(kv)
        self.dantoc = dantoc
        if (self.diem >= 20.5):
            self.stt = "Do"
        else:
            self.stt = "Truot"

    def __str__(self):
        return f"{self.mts} {self.ten} " + "{:.1f}".format(self.diem) + f" {self.stt}"

tts = []
for i in range(int(input())):
    tmp = thiSinh(i+1, input().strip(), float(input()),
                  input().strip(), int(input()))
    tts.append(tmp)
tts.sort(key=lambda x: (-x.diem, x.mts))
for ts in tts:
    print(ts)
```


## String
```python
print("%.2f" % floatNumber) #in 2 số sau dấu phẩy : 
val = f’{:.2f}’.format(floatnum) #lấy 2 số sau dấu phẩy : 
return round(S, 6)
#### In ra 6 số thập phân sau số 0
print(f'{result:.6f}')
s = s[::-1] #reverse
###
self.ma = "VDV"+ format(ma, '02d')
return f"{self.id} {self.ten}{self.initTime} {self.uuTien} {self.afterTime}"
self.dob[6:] # Lấy toàn bộ từ ký tự thứ 6 trở đi
# KY TU THU K
def solve(n, k):
    if k == 2 ** (n-1): return n
    if k > 2 ** (n-1): return solve(n-1, k-2**(n-1))
    else: return solve(n-1, k)
for _ in range(int(input())):
    n, k = list(map(int, input().split()))
    print(chr(solve(n, k) + ord('A') - 1))
```

## Matrix
```python
import numpy as np
a = [
    [1, 2],
    [3, 4],
    [5, 6],
    [7, 8]
]
newa = list(zip(*a))
mat1 = np.array(a)
mat2 = np.array(newa)
mat3 = np.dot(mat1, mat2)
print(a) [[1, 2], [3, 4], [5, 6], [7, 8]]
print(newa) [(1, 3, 5, 7), (2, 4, 6, 8)]
print(mat3) [[  5  11  17  23]
			 [ 11  25  39  53]
			 [ 17  39  61  83]
			 [ 23  53  83 113]]
```

## Dictionary
```python
my_dict = {'a': 1, 'b': 2, 'c': 3}
value = my_dict.get('b')  # returns 2
all_keys = my_dict.keys()  # returns a view object containing keys
all_values = my_dict.values()  # returns a view object containing values
all_items = my_dict.items()  # returns a view object containing (key, value) pairs
popped_value = my_dict.pop('b')  # removes the item with key 'b' and returns its value
my_dict.update({'b': 3, 'c': 4})  # updates the dictionary with new key-value pairs
my_dict.update({'d': 4}) # Adding a new key-value pair
# Sort by keys and then values
sorted_dict = dict(sorted(my_dict.items(), key=lambda item: (item[0], item[1])))
###############
dict = {}
for tmp in a:
    if tmp not in dict:
        dict[tmp] = 1
    else:
        dict[tmp] = dict[tmp] + 1
for x in dict.keys():
    if (dict[x] >= k):
        print(x, dict[x])
###############
for topic, num_questions in topic_questions.items():
    print(f"{topic}: {num_questions}")
###############
students = []
for _ in range(int(input())):
    s = input()
    c, t = map(int, input().split())
    students.append({"name": s, "c": c, "t": t})
    sorted_students = sorted(students, key=lambda x : (-x["c"], x["t"]))
for s in sorted_students:
    print(f'{s["name"]} {s["c"]} {s["t"]}')
```

## Lists
- `arr[start:stop]`        # items start through stop-1
- `arr[start:]`          # items start through the rest of the array
- `arr[:stop]`           # items from the beginning through stop-1
- `arr[:]`            # a copy of the whole array
- `arr[start:stop:step]`    # start through not past stop, by step
- đảo ngược chuỗi : `s1=s[::-1]`
- lấy n ký tự cuối cùng : `s1=s[-n:]`

```python
my_list.insert(1, 4) # inserts 4 at index 1
my_list.remove(2) # removes the first occurrence of 2
popped_element = my_list.pop(1) # removes and returns the element at index 1
index = my_list.index(2) # returns the index of the first occurrence of 2
count = my_list.count(2) # returns the number of occurrences of 2
my_list.reverse() # reverses the list in place
```
## READ .IN, .TXT
`f = open(filename, mode)`
Các mode : 
	r : read only
	w : write only
	a : append only 
	r+ : đọc và ghi dữ liệu vào file, có ghi đè dữ liệu cũ
	w+ : ghi và đọc dữ liệu, không ghi đè dữ liệu cũ
	a+ : nối và đọc dữ liệu từ file
```python
f = open('C:\\Users\\ADMIN\\Tung\\Code\\Python\\DATA.in')
f = open('DATA.in')
t = int(f.readline()) # ~ input()
```
## READ JSON
```python
import json
with open('Book1.json', 'r') as f:
    data = json.load(f)

print(data)
print(data['name'])
print(type(data))
# {'name': 'Bob', 'languages': ['English', 'French']}
# Bob
# <class 'dict'>
```
## READ CSV
```js
stt,name,dacdiem
1,tung,dep trai
2,phong,ngu
3,nam,binh thuong
```
```python
import csv
file_path = 'Book1.csv'
with open(file_path, 'r', newline='', encoding='utf-8') as csvfile:
    csv_reader = csv.reader(csvfile)
    # Skip the header row if it exists
    header = next(csv_reader, None)
    if header:
        print(f'Header: {header}')
    # Iterate through the rows and print the data
    for row in csv_reader:
        stt, name, dacdiem = row
        print(f'STT: {stt}, Name: {name}, Dac diem: {dacdiem}')
```
## DATETIME
```python
from datetime import datetime
self.d1 = datetime.strptime(dateIn, "%d/%m/%Y")
self.d2 = datetime.strptime(dateOut, "%d/%m/%Y")
time_diff = self.d1-self.d2
# tính ngày
self.days = abs(time_diff.days) + 1
```
## Sieve
```python
prime = [True] * 1001
def SieveOfPrime():
    prime[0] = prime[1] = False
    for i in range(2, 1001):
        if prime[i]:
            for j in range(i * i, 1001 , i):
                prime[j] = False
```
## Class
```python
class MyClass:
    def __init__(self, value):
        self.value = value
    def __lt__(self, other): # ~ compareTo
        # Define the less-than comparison logic
        return self.value < other.value
```

## REGEX
Các dạng regex hay dùng 
	tìm các từ ( chữ , không có số ) 
		“\w+” hoặc “[a-zA-Z]+”
	tìm các từ có độ dài n
		"\b\w{n}\b"
	tìm các số 
		“\d+”  [0-9]+
	tách các từ và các số
		‘\b\w+\b’  
		[a-zA-Z0-9]+
	tìm các khoảng trắng
		“s+” 
	tìm cách cụm không có khoảng trắng
		“S+”
```python
s = input().lower()
res += re.findall(r'\b\w+\b', s) #Tìm tất cả các từ, không lẫn với kí tự .,/!;:?
###############
```
## Permutation và Combination
```python
from itertools import permutations
# Define an iterable (e.g., a list)
my_list = [1, 2, 3]
# Generate permutations of length 2
perm = permutations(my_list, 2) #`list`
OUTPUT
(1, 2)
(1, 3)
(2, 1)
(2, 3)
(3, 1)
(3, 2)
```

## Set
- #UNORDERED
- `add(element)` : 
	- thêm 1 phần tử vào set
- `remove(element)`: 
	- Loại bỏ một phần tử khỏi set. Nếu phần tử không tồn tại, sẽ xảy ra lỗi KeyError.
- `discard(element)`: 
	- Loại bỏ một phần tử khỏi set. Không xảy ra lỗi nếu phần tử không tồn tại.

```python
my_list = [1, 2, 2, 3, 4, 4, 5]
unique_elements = set(my_list)

set1 = {1, 2, 3, 4, 5}
set2 = {3, 4, 5, 6, 7}
union_set = set1.union(set2) # {1, 2, 3, 4, 5, 6, 7}
intersection_set = set1.intersection(set2) # {3, 4, 5}
diff = set1.difference(set2) #in set1 but not in set2. {1, 2}

set1 = {1, 2, 3, 4, 5}
set2 = {2, 3}
is_subset = set2.issubset(set1) # True
is_superset = set1.issuperset(set2) # True
symmetric_diff = set1.symmetric_difference(set2) # symmetric_diff = {1, 4, 5}
```


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

## Other
#### [print in reverse] `for char in s[::-1]: `
#### [traverse in reverse] `for i in range(len(text) - 1, -1, -1):`


- ## Basic def
#### All digit is Even/odd
- `def is_all_even(number):

    number_str = str(number)

    for digit in number_str:

        if int(digit) % 2 == 1:

            return False

    return True`
 
#### Palindrome check
- `def is_palindrome(s):

    s = s.lower()  # Convert the string to lowercase to make it case-insensitive

    s = s.replace(" ", "")  # Remove spaces from the string

    return s == s[::-1]`

#### Loop with i+=2
- `for i in range(1, N + 1, 2)`

#### In ra 6 số thập phân sau số 0
- `return round(S, 6)`
- `print(f'{result:.6f}')`
## Advanced def

### Dictionary

```python
# Đọc tổng số dòng dữ liệu
total_lines = int(input())
# Khởi tạo một từ điển để lưu trữ thông tin về các chủ đề và số lượng câu hỏi tương ứng
topic_questions = {}
current_topic = ""

# Duyệt qua từng dòng dữ liệu
for _ in range(total_lines):
    line = input().strip()
    # Kiểm tra xem dòng hiện tại có phải là chủ đề mới hay không
    if not line:
        current_topic = ""
    elif current_topic == "":
        current_topic = line
        topic_questions[current_topic] = 0
    else:
        topic_questions[current_topic] += 1

for topic, num_questions in topic_questions.items():
    print(f"{topic}: {num_questions}")
```

### Array of Dictionaries
```python
import math

students = []
for _ in range(int(input())):
    s = input()
    c, t = map(int, input().split())
    students.append({"name": s, "c": c, "t": t})
    sorted_students = sorted(students, key=lambda x : (-x["c"], x["t"]))
for s in sorted_students:
    print(f'{s["name"]} {s["c"]} {s["t"]}')
```
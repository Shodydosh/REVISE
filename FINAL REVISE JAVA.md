## Input
```java
// FILE NHI PHAN
DataInputStream stream = new DataInputStream(new FileInputStream(“DATA.in”));
while(stream.available() > 0){
	int x = stream.readInt();
}
// FILE NHI PHAN CHUA OBJ
ObjectInputStream stream = new ObjectInputStream(new FileInputStream(“DATA.in”));
ArrayList<Integer> list = (ArrayList<Integer>) stream.readObject()
```
## Set
```java
Set<String> hashSet = new HashSet<>(); // HashSet chứa các phần tử không trùng lặp
Set<String> treeSet = new TreeSet<>(); // HashSet sắp xếp
Set<String> linkedHashSet = new LinkedHashSet<>(); // Hashset không sắp xếp

hashSet.add(), .remove(), .contains(), size(), isEmpty()
hashSet.addAll(anotherSet); //Thêm tất cả các phần tử từ một collection vào set.
hashSet.removeAll(anotherSet); //Loại bỏ tất cả các phần tử của một collection khỏi set
set.retainAll(anotherSet); //Chỉ giữ lại các phần tử có trong cả set và một collection khác, loại bỏ những phần tử khác.
boolean isEqual = set.equals(anotherSet); // So sánh set với một set khác
Object[] array = set.toArray(); // chuyển set thành mảng
```
## String
```java
String[] sentence = s.split("[.!?]"); // split bằng .!?
//
String.format("%.1f", this.diemUuTien)
String.format("%.2e", 123456789.987654) // 1.23e+08
// LAM TRON SO (3so)
DecimalFormat df = new DecimalFormat("#.###");
String formattedNum = df.format(num);
```
## Date, time formatting
- Pattern `HH`: giờ trong ngày (24h) / `hh`: giờ trong ngày (12h)
- Pattern `MM`: tháng trong năm / `mm`: phút trong giờ
```java
String s = "2023-12-18 14:30:45";
SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
Date dateTime = sdf.parse(s);
System.out.println(dateTime);
```
## Date, time calculating (calendar)
```java
String s = "2023-12-18 14:30:45";
SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
Date dateTime = sdf.parse(s);
System.out.println(dateTime); // Mon Dec 18 14:30:45 ICT 2023
Calendar cld = Calendar.getInstance();
cld.setTime(dateTime);
System.out.println(cld.getTime()); // Mon Dec 18 14:30:45 ICT 2023
cld.add(cld.HOUR_OF_DAY, 10); // +10 tieng -> Tue Dec 19 00:30:45 ICT 2023
cld.add(cld.MONTH, -13); // -13 thang -> Sat Nov 19 00:30:45 ICT 2022
cld.set(Calendar.MONTH, Calendar.AUGUST); // set thang8 Fri Aug 19 00:30:45 ICT 2022
String formattedDate = now.format(formatter);
```
## Map
- `HashMap` không đảm bảo thứ tự của các phần tử, hiệu suất là ưu tiên
- `LinkedHashMap` là một lớp khác trong giao diện Map và giữ cho thứ tự của các phần tử giống như thứ tự chúng được thêm vào
- `TreeMap` giống `HashMap` nhưng có thể truyền Comparator vào để sắp xếp
```java
//public static class .......
Comparator<Person> complexComparator = Comparator
	.comparingInt(Person::getAge)
	.thenComparing(Person::getName);

	// Tạo TreeSet với Comparator
	TreeSet<Person> personSet = new TreeSet<>(complexComparator);
```
```java
put(K key, V value) | get(Object key) | containsKey(Object key)
keySet() | values() | remove(Object key)
// Duyet ca key, value
for (Map.Entry<String, Integer> entry : map.entrySet()) {
	System.out.println("Key: " + entry.getKey() + ", Value: " + entry.getValue());
}
```

## OOP
```java
public static class Pair<A, B>{
	private A key;
	private B val;
	public Pair(A key, B val){
		this.key = key;
		this.val = val;
	}
	public boolean isPrime(){
		int tmpK = Integer.parseInt(String.valueOf(key));
		int tmpV = Integer.parseInt(String.valueOf(val));
		return check(tmpK) && check(tmpV);
	}
}
```
## Regex
1. **Tìm các từ (chữ, không có số):** `"\\b[a-zA-Z]+\\b"`
2. **Tìm các từ có độ dài n:** `"\\b\\w{N}\\b"  // Thay N bằng độ dài mong muốn`
3. **Tìm các số:** `"\\d+"`
4. **Tách các từ và các số:** `"\\b[a-zA-Z0-9]+\\b"`
5. **Tìm các khoảng trắng:** `"\\s+"`
6. **Tìm cách cụm không có khoảng trắng:** `"\\S+"`
7. **Tách ngày tháng YYYY-MM-DD:** `"\\b\\d{4}-\\d{2}-\\d{2}\\b"`
8. **Tách n số:** `"\\b\\d{N}\\b"  // Thay N bằng số lượng số mong muốn`
    
```java
String s = "12341234Hello, 123 Wo3rld!";
String regex = "\\d+"; // Matches one or more digits

Pattern pattern = Pattern.compile(regex); // Compile the pattern -> Pattern object
Matcher matcher = pattern.matcher(s); // Matcher to apply the pattern

while (matcher.find()) {
	System.out.print(matcher.group()+ " "); // 12341234 123 3
}
```
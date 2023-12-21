Ứng dụng - Trình diễn - Phiên - Giao vận - Mạng - Liên kết - Vật lý
Application - Presentation - Session - Transport - Network - Data Link - Physical
Data - Segment - Frame - Packet - Bit
N cung cấp các dịch vụ cho N+1
Độ phức tạp của giao thức truyền tin cậy - Đặc tính của kênh truyền
Lớp A cho phép mượn 15 bit chia subnet
### Tầng ứng dụng
	message (thông điệp)
	
### Tầng liên kết dữ liệu - Datalink
	Tạo khung(Frame)
	Switch
	địa chỉ vật lý => địa chỉ logic
	Kiểm soát lỗi và kiểm soát luồng dữ liệu
### Tầng trình diễn - Presentation
	data
	JPG
### Tầng mạng - Network
	Datagram, gói tin(packed)
	chọn đường, chuyển giao thông điệp
	IP, ROUTER - RIP
	dựa vào IP đích trong packet để định tuyến
### Tầng giao vận - Transport
	chuyển giao các thông điệp, truyền tin giữa các tiến trình trên các thiết bị
	kiểm soát lỗi, đóng gói dữ liệu
	giao thức TCP làm việc
### Tầng phiên
	Điều khiển các cuộc liên lạc

### UDP
	Không đòi hỏi độ tin cậy cao
	dữ liệu bắt đầu từ byte thứ 9
	không cần thiết lập kết nối trước khi truyền
	điện thoại, hội thảo
	tầng transport
	Check sum 16bit
### TCP 
	Yêu cầu kết nối: ACK = 0, SYN = 1
	Web, DNS, file
	độ tin cậy cao
	host to host
### Bridge
	Kết nối 2 mạng LAN lại với nhau đồng thời đóng vai trò như một bộ lọc (filter): 
	chỉ cho phép các packet, mà địa chỉ đích nằm ngoài nhánh LAN mà packet xuất phát, 
	đi qua.
### Switch 
	Giảm xung đột
	kết nối các mạng bị chia nhỏ, tránh xung đột
### HUB
	Khuếch đại
### CSMA/CD 
	Carrier Sense Multiple Access/ Collision Detection
	vòng - RING
	nghe lưu thông trên đường truyền
	Ethernet
### Router 
	Định tuyến một gói tin
	trả lời với địa chỉ MAC của mình
	nối các mạng và kiểm soát được broadcast
### Modem
	Truyền dữ liệu đi xa

!md test - tạo thư mục
`Fast Ethernet` - 100baseT
Trình điều khiểu driver - Phần mềm
`Proxy` - Là máy đại diện cho một nhóm máy đi thực hiện một dịch vụ máy khách
Vi phạm an toàn thông tin - Can thiệp vào các hoạt động của mạng
Sự toàn vẹn thông điệp - Ng gửi và ng nhận muốn đảm bảo thông điệp không bị thay đổi
`telnet ip/host` - ip là địa chỉ IP của thiết bị đầu cuối, host là tên thiết bị đầu cuối, port là cổng để giao tiếp với thiết bị đầu cuối
Sợi cáp xoắn nối giữa card mạng với hub - Bấm thứ tự 2 đầu cáp giống nhau
`TCP/IP` - Dùng trong mô hình mạng WAN

`RSA` - Mã hóa công khai
`ADSL (Asyncmetric Digital Subcriber Line)` - Không đối xứng
`DES (Data Encryption Standard)` - Có đối xứng

`WAN` - TCP/IP
`LAN` - TCP/IP, NetBEUI, IPX/SPX
`nenstat` - liệt kê tất cả kết nối vào ra máy tính
### Ping
	Kiểm tra các máy tính trong mạng có liên thông không
	Kiểm tra sự kết nối mạng
### Tracert
	![[Pasted image 20231221214512.png]]
	Phát hiện đường truyền
### ATM
	Độ dài khung cố định (53 bytes)
	155 -> 622 Mbps
### ADSL
	Không đối xứng
bit 1 - 0
bit 2-8 NETID
Giao thức RIP ở router - distance vector routing
:3000 - port giành riêng cho web server
OSPF - link state
header - địa chỉ nguồn và địa chỉ đích
UDP socket - địa chỉ ip nguồn, địa chỉ ip đích
UDP - không đảm bảo dữ liệu đi tới máy đích
UDP - tiến trình nhận ở byte 1 và 2
Truyền tin giữa hai tiến trình
router - định tuyến
ICMP đặt trong 
Việt nam - IP lớp C 192 - 223
IP là giao thức không liên kết
ICMP thông báo cho máy tính khác về tình trạng lỗi
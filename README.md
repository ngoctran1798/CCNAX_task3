Người thực hiện: Trần Thị Ngọc  
Ngày cập nhật: 02/11/2017  
-----  
Tên Bài: Network  
-----  
### 1.Network Layer ?  
- **Tầng mạng (tiếng Anh: Network Layer) là tầng thứ ba trong bảy tầng của mô hình OSI.**  
- Tầng này chịu trách nhiệm đáp ứng các yêu cầu dịch vụ từ tầng giao vận và đưa ra những yêu cầu dịch vụ đối với tầng liên kết dữ liệu.  

![img](https://image.slidesharecdn.com/network-1206754309287969-2-130903092039-/95/network-12067543092879692-10-638.jpg?cb=1378200219)  

- Chức Năng:  
  - Tầng mạng có nhiệm vụ:  
      - Xác định việc chuyển hướng   
      - Vạch đường các gói tin trong mạng (chức năng định tuyến)  
      - Các gói tin này có thể phải đi qua nhiều chặng trước khi đến được đích cuối cùng.  
  - Lớp 3 là lớp có liên quan đến các địa chỉ logic trong mạng Các giao thức hay sử dụng ở đây là IP, RIP, IPX, OSPF, AppleTalk.  
 -----   
 Tên Bài: Internet Protocol  
 -----  
 ### 1.Khái Niệm?  
 - **Internet Protocol (tiếng Anh, viết tắt: IP, có nghĩa là Giao thức Internet)**: là một giao thức hướng dữ liệu được sử dụng bởi các máy chủ nguồn và đích để truyền dữ liệu trong một liên mạng chuyển mạch gói.   
 ![img](http://hoclamit.com/wp-content/uploads/2015/04/can-ban-ve-dia-chi-ip.gif)  
 ### 2.Đặc tính?    
- Dữ liệu trong một liên mạng IP được gửi theo các khối được gọi là các gói *(packet hoặc datagram)*.  
- IP cung cấp một dịch vụ gửi dữ liệu không đảm bảo *(còn gọi là cố gắng cao nhất)*, nghĩa là nó hầu như không đảm bảo gì về gói dữ liệu. Gói dữ liệu có thể đến nơi mà không còn nguyên vẹn, nó có thể đến không theo thứ tự (so với các gói khác được gửi giữa hai máy nguồn và đích đó), nó có thể bị trùng lặp hoặc bị mất hoàn toàn.
- Các thiết bị định tuyến liên mạng chuyển tiếp các gói tin IP qua các mạng tầng liên kết dữ liệu được kết nối với nhau. Việc không có đảm bảo về gửi dữ liệu có nghĩa rằng các chuyển mạch gói có thiết kế đơn giản hơn.  
-----  
Tên Bài:IP Header  
-----  
### 1.IP Header?  
**Internet Protocol (IP) là một giao thức liên mạng hoạt động ở tầng Network trong mô hình OSI.** IP quy định cách thức định địa chỉ các máy tính và cách thức chuyển tải các gói tin qua một liên mạng. IP được đặc tả trong bảng báo cáo kỹ thuật có tên **Request For Comments (RFC)**. IP có hai chức năng chính: cung cấp dịch vụ truyền tải các gói tin qua một liên mạng, phân mảnh và hợp lại các gói tin. Các gói dữ liệu xuất phát từ tầng Application, đến tầng Network được thêm vào một cấu trúc IP Header. Gói dữ liệu sau khi được thêm vào cấu trúc IP Header thì được gọi là IP Diagram (Packet). *Hiện nay, có hai phiên bản IP là IP Version 4 (IPv4) và IP Version 6 (IPv6), do đó có 2 cấu trúc tương ứng là IP Header Version 4 và IP header Version 6.*
- **IPv4:** gồm 12 trường bắt buộc với tổng chiều dài là 20 byte (không tính các trường Options và Data).  
![img](http://hatangmang.blogspot.com/2014/06/ip-header-va-van-e-inh-tuyen.html)  
  - **Version (4 bit):** Chỉ ra phiên bản IP đang được dùng là IPv4 (0100). Nếu trường này khác với phiên bản IP của thiết bị nhận, thiết bị nhận sẽ từ chối và loại bỏ các gói tin này. Bằng cách nhìn vào số phiên bản, Router có thể xác định phần còn lại của IP Datagram.  
  - **IP Header Length (IHL) (4 bit):** Chỉ ra chiều dài của header, mỗi đơn vị là 1 word, mỗi word = 32 bit = 4 byte. Ở đây trường IP Header Length có 4 bit nên có 2^4 = 16 word = 16 x 4byte = 64 byte nên chiều dài header tối đa là 64 byte. Bình thường Hearder dài 20 byte. Đây là chiều dài của tất cả các thông tin Header.  
  - **Type Of Services (TOS) (8 bit):** Chỉ ra cách thức xử lý gói dữ liệu, có độ ưu tiên hay không, độ trễ cho phép của gói dữ liệu. Trường này thường được dùng để thực hiện quản lý chất lượng dịch vụ mạng.  
  - **Total Length (16 bit):** Chỉ ra chiều dài của toàn bộ IP Datagram tính theo byte, bao gồm data và phần header. Do có 16 bit nên tối đa là 2^16 = 65536 byte = 64 Kb nên chiều dài tối đa của 1 IP Datagram là 64 Kb.  
  - **Identification (16 bit):** Chỉ mã số của  1 IP Datagram , giúp bên nhận có thể ghép các mảnh của 1 IP Datagram lại với nhau vì IP Datagram phân thành các mảnh và  các mảnh thuộc cùng  1 IP  Datagram sẽ có cùng Identification.  
  - **Flag (3 bit):** Bit 0: không dùng, Bit 1: cho biết gói có phân mảnh hay không, Bit 2: nếu gói IP Datagram bị phân mảnh thì mảnh này cho biết mảnh này có phải là mảnh cuối không. Bao gồm 6 cờ: URG – cờ cho trường Urgent pointer, ACK – cờ cho trường Acknowledgement, PSH – hàm Push, RST – thiết lập lại đường truyền, SYN – đồng bộ lại số thứ tự, FIN – không gửi thêm dữ liệu.  
  - **Fragment Offset (13 bit):** Báo bên nhận vị trí offset của các mảnh so với gói IP datagram gốc  để có thể ghép lại thành IP datagram gốc.  
  - **Time To Live (TTL) (8 bit):** Chỉ ra số bước nhảy (hop) mà một gói có thể đi qua. Con số này sẽ giảm đi 1, khi gói tin đi qua 1 router. Khi router nào nhận gói tin thấy  TTL đạt tới 0 gói này sẽ bị loại. Đây là giải pháp nhằm ngăn chặn tình trạng lặp vòng vô hạn của gói tin trên mạng.  
  - **Protocol (8 bit):** Chỉ ra giao thức nào của tầng trên (tầng Transport) sẽ nhận phần data sau khi công đoạn xử lí IP diagram ở tầng Network hoàn tất hoặc chỉ ra giao thức nào của tầng trên gởi segment xuống cho tầng Network đóng gói thành IP Diagram, mỗi giao thức có 1 mã (06:  TCP, 17: UDP, 01:  ICMP…).  
  - **Header CheckSum (16 bit):** Hỗ trợ cho Router phát hiện lỗi bit trong khi nhận IP datagram. Giúp bảo đảm sự toàn vẹn của IP Header.  
  - **Source IP Address (32 bit):** Chỉ ra địa chỉ của thiết bị truyền IP diagram (Xem cấu trúc của địa chỉ IPv4).  
  - **Destination IP Address (32 bit):** Chỉ ra địa chỉ IP của thiết bị sẽ nhận IP diagram (Xem cấu trúc của địa chỉ IPv4).  
  - **IP Option:** kích thước không cố định, chứa các thông tin tùy chọn như: Time stamp – thời điểm đã đi qua Router, Security – cho phép Router nhận gói dữ liệu không, nếu không thì gói sẽ bị hủy, Record Router – lưu danh sách địa chỉ IP của Router mà gói phải đi qua, Source Route – bắt buộc đi qua Router nào đó. Lúc này sẽ không cần dùng bảng định tuyến ở mỗi Router nữa.  
  - **Padding:** Các số 0 được bổ sung vào trường này để đảm bảo IP Header luôn là bội số của 32 bit.  

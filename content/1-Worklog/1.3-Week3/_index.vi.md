
---
title: "Worklog Tuần 3"
date: 2026-10-19
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

- Tìm hiểu tổng quan về Amazon Virtual Private Cloud (Amazon VPC), hiểu vai trò của VPC trong việc xây dựng và quản lý môi trường mạng ảo riêng biệt trên AWS.
- Nắm được các khái niệm cơ bản về địa chỉ IP, CIDR, Availability Zone và cách phân chia mạng thành các Subnet để tổ chức tài nguyên AWS.
- Tìm hiểu chức năng và cách hoạt động của các thành phần mạng trong VPC, bao gồm Subnet, Route Table, Internet Gateway (IGW) và NAT Gateway.
- Hiểu các cơ chế bảo mật mạng trong VPC thông qua Security Group và Network Access Control List (Network ACL), đồng thời phân biệt phạm vi áp dụng và cơ chế hoạt động của từng thành phần.
- Có kiến thức và kinh nghiệm thực hành trong việc tạo VPC, cấu hình Subnet, Internet Gateway, Route Table, Security Group và VPC Flow Logs.
- Tìm hiểu cách triển khai Amazon EC2 Instance trong Public Subnet và Private Subnet, thiết lập kết nối SSH, cấu hình NAT Gateway và kiểm tra khả năng kết nối mạng.
- Làm quen với các công cụ phân tích và giám sát mạng AWS, bao gồm VPC Resource Map, VPC Reachability Analyzer, AWS Systems Manager Session Manager và Amazon CloudWatch.
- Tìm hiểu AWS Site-to-Site VPN và nguyên lý thiết lập kết nối mạng an toàn giữa môi trường On-premises và Amazon VPC thông qua các đường hầm VPN được mã hóa.
- Có kiến thức thực hành trong việc cấu hình Virtual Private Gateway (VGW), Customer Gateway (CGW), VPN Connection và phần mềm Libreswan để thiết lập kết nối Site-to-Site VPN.
- Nắm được quy trình giám sát VPN Tunnel, tùy chỉnh các thông số kết nối, xử lý sự cố và dọn dẹp tài nguyên AWS nhằm hạn chế các chi phí phát sinh ngoài dự kiến.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu tổng quan về Amazon Virtual Private Cloud (Amazon VPC) và vai trò của VPC trong việc tạo môi trường mạng ảo riêng biệt trên AWS.<br>- Tìm hiểu kiến trúc mạng VPC và các đặc điểm cơ bản:<br>&nbsp;&nbsp;+ VPC: Mạng ảo riêng biệt trong AWS, cho phép người dùng kiểm soát cấu hình mạng và triển khai tài nguyên.<br>&nbsp;&nbsp;+ CIDR: Phạm vi địa chỉ IP được cấp phát cho VPC và các Subnet.<br>&nbsp;&nbsp;+ Availability Zone (AZ): Các vùng sẵn sàng độc lập trong một AWS Region, hỗ trợ triển khai tài nguyên có tính sẵn sàng cao.<br>- Tìm hiểu các loại Subnet:<br>&nbsp;&nbsp;+ Public Subnet: Subnet có tuyến đường đến Internet thông qua Internet Gateway.<br>&nbsp;&nbsp;+ Private Subnet: Subnet không có tuyến đường trực tiếp đến Internet Gateway.<br>&nbsp;&nbsp;+ VPN-only Subnet: Subnet có các tuyến đường đến Virtual Private Gateway để kết nối thông qua VPN.<br>- Tìm hiểu Route Table và các thành phần của một tuyến đường:<br>&nbsp;&nbsp;+ Destination: Địa chỉ đích của lưu lượng mạng.<br>&nbsp;&nbsp;+ Target: Gateway hoặc thành phần đích tiếp nhận lưu lượng.<br>- Tìm hiểu Internet Gateway (IGW), chức năng kết nối VPC với Internet và cách cấu hình IGW trong Route Table.<br>- Tìm hiểu NAT Gateway, vai trò cho phép tài nguyên trong Private Subnet khởi tạo kết nối ra Internet mà không cần cho phép Internet khởi tạo kết nối trực tiếp đến các tài nguyên đó.<br>- Phân biệt chức năng giữa NAT Gateway và NAT Instance.<br>- Tìm hiểu kiến trúc mạng nhiều Availability Zone (Multi-AZ) và lợi ích của việc phân bố tài nguyên trên nhiều AZ để tăng khả năng sẵn sàng. | 19/10/2026 | 19/10/2026 | [Amazon VPC and AWS Site-to-Site VPN Workshop](https://000003.awsfcaj.com/) |
| 3 | - Tìm hiểu các cơ chế bảo mật mạng trong Amazon VPC:<br>&nbsp;&nbsp;+ Security Group: Tường lửa ảo kiểm soát lưu lượng vào và ra tại cấp độ Network Interface hoặc tài nguyên được liên kết.<br>&nbsp;&nbsp;+ Network ACL (NACL): Cơ chế kiểm soát lưu lượng mạng tại cấp độ Subnet.<br>- Phân biệt Security Group và Network ACL về phạm vi áp dụng và cơ chế hoạt động:<br>&nbsp;&nbsp;+ Security Group hoạt động theo cơ chế Stateful, tự động cho phép lưu lượng phản hồi của kết nối đã được cho phép.<br>&nbsp;&nbsp;+ Network ACL hoạt động theo cơ chế Stateless, cần cấu hình quy tắc cho cả lưu lượng vào và ra.<br>- Tìm hiểu Inbound Rules và Outbound Rules, cách xác định giao thức, Port Range và Source/Destination khi thiết lập quy tắc bảo mật.<br>- Làm quen với VPC Resource Map để quan sát mối quan hệ giữa VPC, Subnet, Route Table, Internet Gateway và các thành phần mạng liên quan.<br>- **Thực hành:** Xây dựng môi trường mạng Amazon VPC trên AWS Management Console.<br>&nbsp;&nbsp;+ Truy cập dịch vụ VPC và tạo một Custom VPC với tên ASG.<br>&nbsp;&nbsp;+ Cấu hình dải địa chỉ IPv4 CIDR `10.10.0.0/16` cho VPC.<br>&nbsp;&nbsp;+ Bật Enable DNS Hostnames và Enable DNS Resolution trong VPC Settings.<br>&nbsp;&nbsp;+ Tạo các Public Subnet và Private Subnet trong những Availability Zone được lựa chọn.<br>&nbsp;&nbsp;+ Tạo Internet Gateway và gắn vào VPC ASG.<br>&nbsp;&nbsp;+ Tạo Route Table cho Public Subnet và cấu hình tuyến đường mặc định `0.0.0.0/0` đến Internet Gateway.<br>&nbsp;&nbsp;+ Liên kết các Subnet với Route Table phù hợp.<br>&nbsp;&nbsp;+ Tạo Security Group và cấu hình Inbound Rules, Outbound Rules theo yêu cầu kết nối.<br>&nbsp;&nbsp;+ Tìm hiểu cách cấu hình Network ACL để kiểm soát lưu lượng ở cấp độ Subnet.<br>&nbsp;&nbsp;+ Kích hoạt VPC Flow Logs để ghi nhận và theo dõi lưu lượng IP đi đến và đi ra khỏi các Network Interface.<br>- Kiểm tra VPC Resource Map để xác nhận cấu trúc và mối quan hệ giữa các thành phần mạng sau khi cấu hình. | 20/10/2026 | 20/10/2026 | [Amazon VPC and AWS Site-to-Site VPN Workshop](https://000003.awsfcaj.com/) |
| 4 | - **Thực hành:** Triển khai Amazon EC2 Instance trong môi trường VPC đã tạo.<br>&nbsp;&nbsp;+ Truy cập dịch vụ Amazon EC2 và lựa chọn Launch instances.<br>&nbsp;&nbsp;+ Tạo EC2 Public và EC2 Private theo kiến trúc của workshop.<br>&nbsp;&nbsp;+ Lựa chọn Amazon Machine Image (AMI) và Instance Type phù hợp.<br>&nbsp;&nbsp;+ Cấu hình Key Pair, VPC, Subnet và Security Group cho từng EC2 Instance.<br>&nbsp;&nbsp;+ Kiểm tra địa chỉ IP công khai, địa chỉ IP riêng và trạng thái hoạt động của các EC2 Instance.<br>- **Thực hành:** Kiểm tra khả năng kết nối đến EC2 Instance.<br>&nbsp;&nbsp;+ Thiết lập kết nối SSH đến EC2 Instance bằng Visual Studio Code với tiện ích Remote - SSH theo hướng dẫn workshop.<br>&nbsp;&nbsp;+ Kiểm tra khả năng kết nối giữa các EC2 Instance và các thành phần trong VPC.<br>&nbsp;&nbsp;+ Kiểm tra kết nối Internet từ các tài nguyên được cấu hình trong Public Subnet.<br>- **Thực hành:** Tạo và cấu hình NAT Gateway.<br>&nbsp;&nbsp;+ Cấp phát Elastic IP Address phục vụ NAT Gateway.<br>&nbsp;&nbsp;+ Tạo Public NAT Gateway trong Public Subnet phù hợp.<br>&nbsp;&nbsp;+ Liên kết NAT Gateway với Elastic IP đã cấp phát.<br>&nbsp;&nbsp;+ Cấu hình Route Table của Private Subnet với tuyến đường mặc định `0.0.0.0/0` trỏ đến NAT Gateway.<br>&nbsp;&nbsp;+ Kiểm tra khả năng truy cập Internet theo chiều đi ra từ EC2 Instance trong Private Subnet.<br>- Tìm hiểu VPC Reachability Analyzer và cách sử dụng công cụ để phân tích đường đi kết nối mạng, kiểm tra cấu hình Security Group, Network ACL và xác định nguyên nhân gây gián đoạn kết nối.<br>- Tìm hiểu EC2 Instance Connect Endpoint như một phương thức kết nối EC2 bổ sung (nội dung tùy chọn).<br>- Tìm hiểu AWS Systems Manager Session Manager và cách truy cập EC2 Instance an toàn thông qua trình duyệt mà không cần sử dụng SSH Key hoặc mở cổng SSH Inbound.<br>- Tìm hiểu CloudWatch Monitoring & Alerting, cách theo dõi các chỉ số hoạt động của EC2, NAT Gateway, VPN Connection và VPC Flow Logs.<br>- Tìm hiểu cách thiết lập cảnh báo CloudWatch để hỗ trợ giám sát tài nguyên và phát hiện các vấn đề về kết nối mạng. | 21/10/2026 | 21/10/2026 | [Amazon VPC and AWS Site-to-Site VPN Workshop](https://000003.awsfcaj.com/) |
| 5 | - Tìm hiểu tổng quan về AWS Site-to-Site VPN và mục đích thiết lập kết nối mạng an toàn giữa môi trường On-premises và Amazon VPC.<br>- Tìm hiểu kiến trúc kết nối Site-to-Site VPN và chức năng của các thành phần:<br>&nbsp;&nbsp;+ Virtual Private Gateway (VGW): Cổng kết nối VPN phía AWS, được gắn với VPC.<br>&nbsp;&nbsp;+ Customer Gateway (CGW): Đại diện cho thiết bị hoặc phần mềm VPN ở phía mạng khách hàng.<br>&nbsp;&nbsp;+ VPN Connection: Kết nối VPN giữa Virtual Private Gateway và Customer Gateway.<br>&nbsp;&nbsp;+ VPN Tunnel: Đường hầm kết nối được mã hóa nhằm truyền dữ liệu an toàn giữa hai môi trường mạng.<br>- **Thực hành:** Xây dựng môi trường mô phỏng Branch Office phục vụ kết nối VPN.<br>&nbsp;&nbsp;+ Tạo một VPC riêng với tên ASG VPN và dải địa chỉ IPv4 CIDR `10.11.0.0/16`.<br>&nbsp;&nbsp;+ Tạo Public Subnet và cấu hình Internet Gateway cho môi trường VPN.<br>&nbsp;&nbsp;+ Tạo Route Table và cấu hình tuyến đường mạng phù hợp.<br>&nbsp;&nbsp;+ Tạo Security Group cho phép các kết nối cần thiết phục vụ VPN, SSH và kiểm tra kết nối theo hướng dẫn workshop.<br>&nbsp;&nbsp;+ Khởi chạy EC2 Instance trong Public Subnet để đóng vai trò môi trường Customer Gateway.<br>&nbsp;&nbsp;+ Kiểm tra địa chỉ IP công khai của EC2 Instance được sử dụng làm Customer Gateway.<br>- **Thực hành:** Tạo các thành phần kết nối AWS Site-to-Site VPN.<br>&nbsp;&nbsp;+ Tạo Virtual Private Gateway với tên VPN Gateway và gắn vào VPC đích.<br>&nbsp;&nbsp;+ Tạo Customer Gateway với địa chỉ IP công khai của EC2 Customer Gateway.<br>&nbsp;&nbsp;+ Cấu hình BGP ASN theo hướng dẫn, sử dụng giá trị mặc định 65000 cho kịch bản định tuyến tĩnh.<br>&nbsp;&nbsp;+ Tạo VPN Connection, lựa chọn Virtual Private Gateway và Customer Gateway đã tạo.<br>&nbsp;&nbsp;+ Lựa chọn Static Routing và khai báo dải địa chỉ mạng `10.11.0.0/16` của môi trường mô phỏng phía Customer Gateway.<br>&nbsp;&nbsp;+ Kiểm tra trạng thái VPN Connection và chờ tài nguyên chuyển sang trạng thái Available. | 22/10/2026 | 22/10/2026 | [Amazon VPC and AWS Site-to-Site VPN Workshop](https://000003.awsfcaj.com/) |
| 6 | - **Thực hành:** Cấu hình Customer Gateway và thiết lập VPN Tunnel.<br>&nbsp;&nbsp;+ Truy cập VPN Connection đã tạo trong VPC Console.<br>&nbsp;&nbsp;+ Tải tệp cấu hình VPN dành cho thiết bị Customer Gateway.<br>&nbsp;&nbsp;+ Lựa chọn Vendor và Platform là OpenSwan, Software là OpenSwan 2.6.38+ và IKE version là IKEv1 theo hướng dẫn workshop.<br>&nbsp;&nbsp;+ Kết nối SSH đến EC2 Instance đóng vai trò Customer Gateway.<br>&nbsp;&nbsp;+ Cài đặt và cấu hình phần mềm Libreswan trên EC2 Instance theo hướng dẫn.<br>&nbsp;&nbsp;+ Kiểm tra và chỉnh sửa cấu hình IPsec trong tệp `/etc/ipsec.conf` khi cần thiết.<br>&nbsp;&nbsp;+ Cấu hình IP Forwarding và các thông số mạng cần thiết trên Customer Gateway.<br>&nbsp;&nbsp;+ Thiết lập cấu hình VPN Tunnel theo tệp cấu hình AWS cung cấp.<br>&nbsp;&nbsp;+ Kiểm tra trạng thái các VPN Tunnel và khả năng kết nối giữa môi trường mạng AWS và Branch Office mô phỏng.<br>- Tìm hiểu cách tùy chỉnh các thông số VPN Tunnel thông qua AWS VPC Console:<br>&nbsp;&nbsp;+ Dead Peer Detection (DPD) Timeout.<br>&nbsp;&nbsp;+ Phiên bản IKE (IKEv1/IKEv2).<br>&nbsp;&nbsp;+ Thuật toán mã hóa (Encryption Algorithms).<br>&nbsp;&nbsp;+ Thuật toán kiểm tra tính toàn vẹn dữ liệu (Integrity Algorithms).<br>&nbsp;&nbsp;+ Diffie-Hellman (DH) Groups.<br>- Tìm hiểu cách kích hoạt VPN Tunnel Activity Logs và sử dụng Amazon CloudWatch Logs để theo dõi hoạt động, sự kiện kết nối và thông tin xác thực VPN.<br>- Tìm hiểu VPN Troubleshooting Guide, cách kiểm tra trạng thái Tunnel, cấu hình IKE/IPsec, định tuyến, IP Forwarding và nhật ký hệ thống để xử lý các sự cố kết nối.<br>- Tìm hiểu các cấu hình VPN thay thế và mô hình kết nối StrongSwan với Transit Gateway theo phần mở rộng tùy chọn của workshop.<br>- Tìm hiểu Infrastructure as Code (IaC) Templates và lợi ích của việc tự động hóa triển khai VPC thông qua các tệp định nghĩa hạ tầng.<br>- **Thực hành:** Kiểm tra và dọn dẹp các tài nguyên AWS được tạo trong bài thực hành theo đúng thứ tự:<br>&nbsp;&nbsp;+ Terminate các EC2 Instance được tạo cho bài thực hành.<br>&nbsp;&nbsp;+ Xóa NAT Gateway.<br>&nbsp;&nbsp;+ Giải phóng Elastic IP Address sau khi không còn sử dụng.<br>&nbsp;&nbsp;+ Xóa VPC Endpoints nếu được tạo.<br>&nbsp;&nbsp;+ Xóa VPN Connection.<br>&nbsp;&nbsp;+ Xóa Virtual Private Gateway.<br>&nbsp;&nbsp;+ Xóa Customer Gateway.<br>&nbsp;&nbsp;+ Xóa các VPC liên quan sau khi đã xử lý các tài nguyên phụ thuộc.<br>- Kiểm tra lại tài nguyên sau khi dọn dẹp nhằm hạn chế các khoản chi phí AWS phát sinh ngoài dự kiến. | 23/10/2026 | 23/10/2026 | [Amazon VPC and AWS Site-to-Site VPN Workshop](https://000003.awsfcaj.com/) |

### Kết quả đạt được trong Tuần 3:

- Nắm được tổng quan về Amazon Virtual Private Cloud (Amazon VPC), hiểu vai trò của VPC trong việc xây dựng môi trường mạng ảo riêng biệt và quản lý các tài nguyên AWS theo cấu hình mạng do người dùng xác định.

- Hiểu được các khái niệm cơ bản về kiến trúc mạng và địa chỉ IP trong VPC, bao gồm:
  - **VPC:** Môi trường mạng ảo được cô lập về mặt logic trong AWS.
  - **CIDR:** Dải địa chỉ IP được sử dụng để xác định phạm vi địa chỉ mạng của VPC và Subnet.
  - **Availability Zone (AZ):** Vùng sẵn sàng độc lập trong một AWS Region, hỗ trợ phân bố tài nguyên và tăng khả năng sẵn sàng.
  - **Subnet:** Phân chia VPC thành các mạng con để tổ chức và quản lý tài nguyên AWS.

- Phân biệt được các loại Subnet theo cấu hình định tuyến và mục đích sử dụng:
  - **Public Subnet:** Có tuyến đường đến Internet thông qua Internet Gateway.
  - **Private Subnet:** Không có tuyến đường trực tiếp đến Internet Gateway, có thể sử dụng NAT Gateway để khởi tạo kết nối ra ngoài Internet.
  - **VPN-only Subnet:** Được cấu hình các tuyến đường đến Virtual Private Gateway để giao tiếp thông qua kết nối VPN.

- Hiểu được chức năng và cách hoạt động của các thành phần định tuyến trong VPC:
  - **Route Table:** Chứa các quy tắc định tuyến, xác định hướng chuyển tiếp lưu lượng mạng thông qua Destination và Target.
  - **Internet Gateway (IGW):** Cho phép các tài nguyên trong VPC giao tiếp với Internet khi được cấu hình địa chỉ IP công khai và tuyến đường phù hợp.
  - **NAT Gateway:** Cho phép các tài nguyên trong Private Subnet khởi tạo kết nối ra Internet hoặc dịch vụ bên ngoài mà không cần cho phép Internet khởi tạo kết nối trực tiếp đến các tài nguyên đó.

- Hiểu được sự khác biệt giữa NAT Gateway và NAT Instance, đồng thời nắm được vai trò của NAT Gateway trong việc hỗ trợ các tài nguyên thuộc Private Subnet truy cập Internet theo chiều đi ra.

- Nắm được kiến trúc Multi-AZ và lợi ích của việc triển khai tài nguyên trên nhiều Availability Zone nhằm tăng khả năng sẵn sàng và hạn chế rủi ro khi một AZ gặp sự cố.

- Hiểu được các cơ chế bảo mật mạng trong Amazon VPC, bao gồm:
  - **Security Group:** Tường lửa ảo kiểm soát lưu lượng vào và ra ở cấp độ Network Interface hoặc tài nguyên được liên kết, hoạt động theo cơ chế Stateful.
  - **Network ACL (NACL):** Cơ chế kiểm soát lưu lượng mạng ở cấp độ Subnet, hoạt động theo cơ chế Stateless.
  - **Inbound Rules:** Quy tắc kiểm soát lưu lượng đi vào tài nguyên.
  - **Outbound Rules:** Quy tắc kiểm soát lưu lượng đi ra khỏi tài nguyên.

- Phân biệt được Security Group và Network ACL về phạm vi áp dụng, cơ chế hoạt động và cách cấu hình quy tắc bảo mật, đồng thời hiểu được tầm quan trọng của việc chỉ cho phép các kết nối cần thiết.

- Làm quen với VPC Resource Map và biết cách sử dụng công cụ để quan sát mối quan hệ giữa VPC, Subnet, Route Table, Internet Gateway và các thành phần mạng khác trong môi trường AWS.

- Hiểu được chức năng của VPC Flow Logs trong việc ghi nhận thông tin lưu lượng IP đi đến và đi ra khỏi các Network Interface, hỗ trợ giám sát bảo mật, phân tích lưu lượng và xử lý sự cố mạng.

- Có kiến thức và kinh nghiệm thực hành trong việc xây dựng môi trường Amazon VPC, bao gồm:
  - Tạo Custom VPC với tên ASG và dải địa chỉ IPv4 CIDR `10.10.0.0/16`.
  - Cấu hình Enable DNS Hostnames và Enable DNS Resolution.
  - Tạo Public Subnet và Private Subnet trong các Availability Zone được lựa chọn.
  - Tạo Internet Gateway và gắn vào VPC.
  - Tạo Route Table và cấu hình tuyến đường mặc định `0.0.0.0/0` đến Internet Gateway cho Public Subnet.
  - Liên kết Subnet với Route Table phù hợp.
  - Tạo và cấu hình Security Group với Inbound Rules và Outbound Rules.
  - Tìm hiểu cấu hình Network ACL để kiểm soát lưu lượng ở cấp độ Subnet.
  - Kích hoạt VPC Flow Logs để theo dõi lưu lượng mạng.

- Có kiến thức và kinh nghiệm thực hành trong việc triển khai Amazon EC2 Instance, bao gồm:
  - Lựa chọn Amazon Machine Image (AMI) và Instance Type phù hợp.
  - Cấu hình Key Pair, VPC, Subnet và Security Group.
  - Triển khai EC2 Instance trong Public Subnet và Private Subnet.
  - Kiểm tra trạng thái hoạt động, địa chỉ IP công khai và địa chỉ IP riêng của EC2 Instance.
  - Thiết lập kết nối SSH đến EC2 thông qua Visual Studio Code và tiện ích Remote - SSH.
  - Kiểm tra khả năng kết nối giữa các tài nguyên trong môi trường VPC.

- Hiểu được cách triển khai NAT Gateway trong Public Subnet, cấp phát và liên kết Elastic IP, đồng thời cấu hình Route Table cho Private Subnet nhằm cho phép EC2 Instance truy cập Internet theo chiều đi ra.

- Làm quen với VPC Reachability Analyzer và biết cách sử dụng công cụ để:
  - Phân tích đường đi kết nối giữa các tài nguyên trong VPC.
  - Kiểm tra khả năng kết nối mạng dựa trên cấu hình hiện tại.
  - Phân tích các quy tắc Security Group và Network ACL.
  - Xác định những thành phần cấu hình có thể ảnh hưởng đến khả năng kết nối.

- Tìm hiểu EC2 Instance Connect Endpoint như một phương thức kết nối bổ sung đến EC2 Instance mà không cần phụ thuộc hoàn toàn vào địa chỉ IP công khai.

- Hiểu được chức năng của AWS Systems Manager Session Manager trong việc truy cập và quản lý EC2 Instance thông qua phiên làm việc tương tác an toàn, có khả năng kiểm toán mà không cần SSH Key hoặc mở cổng SSH Inbound.

- Nắm được vai trò của Amazon CloudWatch trong việc giám sát tài nguyên và lưu lượng mạng, bao gồm:
  - Theo dõi chỉ số hoạt động của NAT Gateway.
  - Giám sát trạng thái VPN Tunnel và lưu lượng dữ liệu.
  - Theo dõi hiệu suất mạng, CPU và bộ nhớ của EC2 Instance khi có chỉ số tương ứng.
  - Theo dõi VPC Flow Logs và các sự kiện bảo mật.
  - Tìm hiểu cách thiết lập cảnh báo khi các chỉ số vượt ngưỡng cấu hình.

- Nắm được tổng quan về AWS Site-to-Site VPN và hiểu cách thiết lập kết nối mạng an toàn giữa môi trường On-premises và Amazon VPC thông qua các đường hầm VPN được mã hóa.

- Hiểu được chức năng của các thành phần chính trong kiến trúc Site-to-Site VPN:
  - **Virtual Private Gateway (VGW):** Cổng kết nối VPN phía AWS, được gắn với VPC để thiết lập kết nối VPN.
  - **Customer Gateway (CGW):** Đại diện cho thiết bị hoặc phần mềm VPN ở phía mạng khách hàng.
  - **VPN Connection:** Thành phần thiết lập kết nối giữa Virtual Private Gateway và Customer Gateway.
  - **VPN Tunnel:** Đường hầm được mã hóa để truyền dữ liệu an toàn giữa hai môi trường mạng.

- Có kiến thức thực hành trong việc xây dựng môi trường mô phỏng Branch Office phục vụ kết nối VPN, bao gồm:
  - Tạo VPC riêng với tên ASG VPN và dải địa chỉ IPv4 CIDR `10.11.0.0/16`.
  - Tạo Public Subnet và cấu hình Internet Gateway.
  - Tạo Route Table và thiết lập các tuyến đường mạng cần thiết.
  - Tạo Security Group phục vụ kết nối VPN, SSH và kiểm tra mạng.
  - Triển khai EC2 Instance trong Public Subnet để đóng vai trò Customer Gateway.
  - Kiểm tra địa chỉ IP công khai của EC2 Instance.

- Có kiến thức thực hành trong việc tạo và cấu hình các thành phần AWS Site-to-Site VPN, bao gồm:
  - Tạo Virtual Private Gateway và gắn với VPC đích.
  - Tạo Customer Gateway bằng địa chỉ IP công khai của EC2 Customer Gateway.
  - Cấu hình BGP ASN theo hướng dẫn của workshop, sử dụng giá trị mặc định 65000 trong kịch bản định tuyến tĩnh.
  - Tạo VPN Connection giữa Virtual Private Gateway và Customer Gateway.
  - Lựa chọn Static Routing và khai báo dải địa chỉ mạng `10.11.0.0/16` của môi trường mô phỏng phía Customer Gateway.
  - Kiểm tra trạng thái VPN Connection và quá trình khởi tạo kết nối.

- Hiểu được quy trình tải và sử dụng tệp cấu hình VPN do AWS cung cấp cho Customer Gateway, bao gồm:
  - Lựa chọn Vendor và Platform là OpenSwan.
  - Lựa chọn Software OpenSwan 2.6.38+.
  - Lựa chọn phiên bản IKEv1 theo hướng dẫn workshop.
  - Sử dụng tệp cấu hình làm cơ sở thiết lập IPsec trên EC2 Customer Gateway.

- Có kiến thức thực hành về cài đặt và cấu hình Libreswan trên EC2 Customer Gateway, bao gồm:
  - Cài đặt phần mềm Libreswan trên môi trường Linux phù hợp.
  - Kiểm tra và cấu hình tệp `/etc/ipsec.conf`.
  - Thiết lập IP Forwarding và các tham số mạng cần thiết.
  - Cấu hình các thông số IPsec theo tệp cấu hình AWS cung cấp.
  - Kiểm tra trạng thái các VPN Tunnel và khả năng truyền dữ liệu giữa hai mạng.

- Hiểu được cách tùy chỉnh các thông số VPN Tunnel, bao gồm DPD Timeout, phiên bản IKE, thuật toán mã hóa, thuật toán kiểm tra tính toàn vẹn dữ liệu và Diffie-Hellman Groups.

- Làm quen với việc kích hoạt VPN Tunnel Activity Logs và sử dụng Amazon CloudWatch Logs để theo dõi hoạt động của đường hầm VPN, sự kiện kết nối và thông tin phục vụ phân tích sự cố.

- Nắm được các bước kiểm tra và xử lý sự cố Site-to-Site VPN, bao gồm:
  - Kiểm tra trạng thái hoạt động của VPN Tunnel.
  - Kiểm tra cấu hình Customer Gateway và VPN Connection.
  - Kiểm tra thông số IKE/IPsec và quá trình xác thực.
  - Kiểm tra IP Forwarding và thông tin định tuyến giữa hai mạng.
  - Kiểm tra cấu hình mạng và nhật ký hệ thống để xác định nguyên nhân gây gián đoạn kết nối.

- Tìm hiểu các cấu hình VPN thay thế và mô hình sử dụng StrongSwan kết hợp Transit Gateway theo phần nội dung mở rộng tùy chọn của workshop.

- Nắm được khái niệm Infrastructure as Code (IaC) và lợi ích của việc quản lý, triển khai hạ tầng AWS thông qua các tệp định nghĩa có thể đọc và xử lý bằng máy tính, bao gồm:
  - Tái sử dụng cấu hình để triển khai môi trường đồng nhất.
  - Quản lý phiên bản và theo dõi thay đổi hạ tầng.
  - Tự động hóa quá trình triển khai nhằm hạn chế sai sót thủ công.
  - Tái tạo hoặc dọn dẹp môi trường một cách có hệ thống.
  - Hỗ trợ chuẩn hóa và kiểm tra cấu hình bảo mật.

- Nhận thức được tầm quan trọng của việc dọn dẹp tài nguyên AWS sau khi hoàn thành bài thực hành, đặc biệt là NAT Gateway, Elastic IP, EC2 Instance và VPN Connection vì các tài nguyên này có thể phát sinh chi phí trong quá trình sử dụng.

- Nắm được thứ tự dọn dẹp tài nguyên theo hướng dẫn workshop nhằm tránh lỗi phụ thuộc giữa các thành phần:
  - Terminate EC2 Instances.
  - Delete NAT Gateways.
  - Release Elastic IP Addresses.
  - Delete VPC Endpoints nếu có.
  - Delete VPN Connections.
  - Detach và delete Virtual Private Gateways.
  - Delete Customer Gateways.
  - Delete VPCs sau cùng.

- Hiểu được rằng việc kiểm tra và dọn dẹp tài nguyên đúng cách giúp hạn chế các khoản phí AWS phát sinh ngoài dự kiến, đồng thời duy trì môi trường tài khoản AWS gọn gàng và dễ quản lý.

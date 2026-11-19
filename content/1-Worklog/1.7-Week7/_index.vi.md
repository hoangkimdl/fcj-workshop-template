---
title: "Worklog Tuần 7"
date: 2026-11-16
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

- Tìm hiểu tổng quan về Amazon Relational Database Service (Amazon RDS), vai trò của dịch vụ cơ sở dữ liệu quan hệ được quản lý trên AWS Cloud và các lợi ích như tự động sao lưu, cập nhật phần mềm, mở rộng tài nguyên và tăng cường tính sẵn sàng.
- Tìm hiểu các hệ quản trị cơ sở dữ liệu được Amazon RDS hỗ trợ, bao gồm Amazon Aurora, MySQL, MariaDB, Oracle, Microsoft SQL Server và PostgreSQL.
- Nắm được các thành phần và tính năng quan trọng của Amazon RDS như DB Instance, DB Endpoint, DB Subnet Group, Storage Options, Automated Backups, Manual Snapshots, Multi-AZ và Read Replicas.
- Tìm hiểu các phương thức bảo mật cơ sở dữ liệu thông qua Amazon VPC, Security Groups, IAM Policies, AWS KMS và SSL/TLS Encryption.
- Thực hành xây dựng môi trường mạng phục vụ triển khai Amazon RDS bằng cách tạo VPC, cấu hình Public Subnets, Private Subnets, Security Groups và DB Subnet Group nhằm kiểm soát kết nối giữa máy chủ ứng dụng và cơ sở dữ liệu.
- Thực hành khởi tạo Amazon RDS Database Instance sử dụng MySQL, cấu hình thông số máy chủ cơ sở dữ liệu, dung lượng lưu trữ, thông tin xác thực, khả năng triển khai Multi-AZ và các thiết lập kết nối bảo mật.
- Thực hành khởi chạy Amazon EC2 Instance sử dụng Amazon Linux 2023, thiết lập Key Pair, Security Group và kết nối đến máy chủ thông qua SSH bằng MobaXterm.
- Thực hành kết nối từ EC2 đến Amazon RDS MySQL thông qua DB Endpoint và MySQL Command Line Client, sử dụng các câu lệnh SQL để tạo cơ sở dữ liệu, tạo bảng, thêm dữ liệu và truy vấn thông tin.
- Thực hành triển khai ứng dụng AWS User Management sử dụng Node.js trên EC2, cấu hình kết nối với Amazon RDS bằng file `.env` và sử dụng PM2 để quản lý tiến trình ứng dụng.
- Tìm hiểu và thực hành chức năng Automated Backups, quản lý Database Snapshots và khôi phục cơ sở dữ liệu trên Amazon RDS nhằm bảo vệ dữ liệu và hỗ trợ Disaster Recovery.
- Nắm được quy trình kiểm tra, dọn dẹp và xóa các tài nguyên Amazon RDS, EC2, DB Subnet Group và VPC sau khi hoàn thành Workshop nhằm hạn chế chi phí phát sinh không cần thiết.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | **Tìm hiểu tổng quan về Amazon RDS và chuẩn bị môi trường mạng bằng Amazon VPC**<br><br> - Tìm hiểu tổng quan về Amazon Relational Database Service (Amazon RDS), một dịch vụ cơ sở dữ liệu quan hệ được AWS quản lý, cho phép triển khai và vận hành cơ sở dữ liệu trên AWS Cloud.<br> - Tìm hiểu vai trò của Amazon RDS trong việc lưu trữ và xử lý dữ liệu có cấu trúc, đặc biệt đối với các ứng dụng sử dụng hệ quản trị cơ sở dữ liệu quan hệ và Online Transaction Processing (OLTP).<br> - Tìm hiểu các lợi ích của Amazon RDS như tự động sao lưu, cập nhật phần mềm cơ sở dữ liệu, quản lý bản vá trong Maintenance Window, mở rộng tài nguyên và hỗ trợ khả năng sẵn sàng cao.<br> - Tìm hiểu các hệ quản trị cơ sở dữ liệu được Amazon RDS hỗ trợ, bao gồm:<br>&nbsp;&nbsp;+ Amazon Aurora.<br>&nbsp;&nbsp;+ MySQL.<br>&nbsp;&nbsp;+ MariaDB.<br>&nbsp;&nbsp;+ Oracle.<br>&nbsp;&nbsp;+ Microsoft SQL Server.<br>&nbsp;&nbsp;+ PostgreSQL.<br> - Phân biệt Amazon RDS với việc tự triển khai cơ sở dữ liệu trên EC2; hiểu rằng RDS là dịch vụ được quản lý nên người dùng không có quyền truy cập root vào máy chủ EC2 nền tảng của RDS, ngoại trừ Amazon RDS Custom đối với một số Database Engine được hỗ trợ.<br> - Tìm hiểu các tính năng quản lý của Amazon RDS, bao gồm bảo mật DB Instance, cập nhật phần mềm, Automated Backups, mở rộng tài nguyên, Multi-AZ và Read Replicas.<br> - Tìm hiểu các tùy chọn lưu trữ của Amazon RDS:<br>&nbsp;&nbsp;+ General Purpose SSD (gp3/gp2): Cung cấp khả năng lưu trữ với chi phí hợp lý, phù hợp với nhiều loại ứng dụng cơ sở dữ liệu.<br>&nbsp;&nbsp;+ Provisioned IOPS SSD (io1/io2): Phù hợp với các hệ thống có yêu cầu cao về hiệu năng đọc ghi dữ liệu.<br>&nbsp;&nbsp;+ Magnetic Storage: Tùy chọn lưu trữ cũ, có hiệu năng hạn chế và không được khuyến nghị cho các triển khai mới.<br> - Tìm hiểu các cơ chế High Availability và Disaster Recovery của RDS, bao gồm Multi-AZ Deployment với cơ chế sao chép đồng bộ, Read Replicas với cơ chế sao chép bất đồng bộ và Global Databases hỗ trợ sao chép liên vùng.<br> - Tìm hiểu các phương thức bảo mật Amazon RDS như mã hóa dữ liệu khi lưu trữ bằng AWS KMS, mã hóa dữ liệu khi truyền bằng SSL/TLS, cô lập mạng thông qua VPC và kiểm soát quyền truy cập bằng IAM Policies.<br> - Tìm hiểu khả năng mở rộng của Amazon RDS, bao gồm mở rộng dung lượng lưu trữ và thay đổi tài nguyên tính toán theo nhu cầu sử dụng.<br> - Tìm hiểu cơ chế Automated Backups hỗ trợ Point-in-Time Recovery với thời gian lưu trữ tối đa 35 ngày và Manual DB Snapshots được lưu giữ cho đến khi người dùng chủ động xóa.<br> - Truy cập AWS Management Console và mở dịch vụ Amazon VPC để chuẩn bị môi trường mạng phục vụ triển khai cơ sở dữ liệu.<br> - Thực hành lựa chọn Create VPC và chọn cấu hình VPC and more để tạo môi trường VPC cùng các thành phần mạng cần thiết.<br> - Đặt tên VPC là `rds`, sử dụng IPv4 CIDR Block `10.0.0.0/16` và lựa chọn Default Tenancy theo hướng dẫn Workshop.<br> - Cấu hình kiến trúc mạng gồm 2 Availability Zones, 2 Public Subnets và 2 Private Subnets, mỗi Availability Zone có một Public Subnet và một Private Subnet.<br> - Không tạo NAT Gateway và VPC Endpoint trong bài thực hành nhằm hạn chế chi phí phát sinh.<br> - Giữ các tùy chọn DNS Resolution và DNS Hostnames theo cấu hình mặc định, sau đó hoàn tất việc tạo VPC.<br> - Kiểm tra các Subnets được tạo trong VPC và thực hành cấu hình Public Subnets bằng cách truy cập Subnets → chọn Public Subnet → Actions → Edit subnet settings.<br> - Bật Enable auto-assign public IPv4 address cho Public Subnets để hỗ trợ kết nối đến EC2 Instance.<br> - Kiểm tra và đảm bảo các Subnets dành cho triển khai RDS không bật tự động cấp phát Public IPv4 nhằm hạn chế nguy cơ cơ sở dữ liệu được truy cập trực tiếp từ Internet.<br> - Kiểm tra tổng thể cấu hình VPC, Availability Zones, Public Subnets và Private Subnets trước khi tiếp tục tạo các thành phần bảo mật. | 16/11/2026 | 16/11/2026 | [Get Started with Amazon RDS](https://000005.awsfcaj.com/)<br>[Introduce](https://000005.awsfcaj.com/1-introduce/)<br>[Create a VPC](https://000005.awsfcaj.com/2-prerequiste/2.1-create-vpc/) |
| 3 | **Thực hành cấu hình Security Groups, DB Subnet Group và khởi tạo Amazon RDS Database Instance**<br><br> - Tìm hiểu Security Groups và vai trò của chúng như các Virtual Firewalls nhằm kiểm soát lưu lượng truy cập Inbound và Outbound của EC2 Instance và RDS Database Instance.<br> - Thực hành truy cập EC2 Console, mở mục Security Groups và lựa chọn Create security group để tạo Security Group dành riêng cho EC2.<br> - Đặt tên Security Group là `ec2-sg`, mô tả `Security group for EC2 instances connecting to RDS` và lựa chọn VPC đã tạo trước đó.<br> - Cấu hình Inbound Rules cho `ec2-sg` bao gồm:<br>&nbsp;&nbsp;+ SSH (22): Chỉ cho phép địa chỉ My IP nhằm phục vụ kết nối và quản trị máy chủ Linux.<br>&nbsp;&nbsp;+ HTTP (80): Cho phép truy cập từ Anywhere-IPv4 để phục vụ lưu lượng Web.<br>&nbsp;&nbsp;+ HTTPS (443): Cho phép truy cập từ Anywhere-IPv4 để hỗ trợ kết nối Web bảo mật.<br>&nbsp;&nbsp;+ Custom TCP (5000): Cho phép truy cập từ Anywhere-IPv4 để kiểm tra ứng dụng Node.js.<br> - Kiểm tra lại các Inbound Rules và hoàn tất việc tạo Security Group `ec2-sg`.<br> - Tiếp tục thực hành tạo Security Group dành riêng cho Amazon RDS với tên `rds-sg`, mô tả `Security group for RDS MySQL database instances` và lựa chọn cùng VPC đã tạo.<br> - Cấu hình Inbound Rule MySQL/Aurora (3306), lựa chọn nguồn truy cập là Security Group `ec2-sg` thay vì mở quyền truy cập cho toàn bộ Internet.<br> - Hiểu được lợi ích của việc sử dụng Security Group làm nguồn truy cập, đảm bảo chỉ các EC2 Instance có Security Group phù hợp mới có thể kết nối đến cơ sở dữ liệu.<br> - Tìm hiểu nguyên tắc tách biệt Security Group giữa máy chủ ứng dụng và máy chủ cơ sở dữ liệu nhằm tăng cường khả năng cô lập tài nguyên và quản lý quyền truy cập.<br> - Truy cập Amazon RDS, lựa chọn Subnet groups → Create DB Subnet Group để tạo nhóm Subnets phục vụ triển khai cơ sở dữ liệu.<br> - Đặt tên DB Subnet Group là `rds-subnet-group`, mô tả `Subnet group for RDS instances` và lựa chọn VPC đã tạo trước đó.<br> - Trong phần Add subnets, lựa chọn các Subnets thuộc ít nhất hai Availability Zones khác nhau, ưu tiên Private Subnets để phục vụ triển khai RDS.<br> - Hoàn tất quá trình tạo DB Subnet Group và kiểm tra danh sách Subnets được liên kết nhằm đảm bảo cấu hình đáp ứng yêu cầu triển khai Multi-AZ.<br> - Truy cập Amazon RDS, lựa chọn Databases → Create database và sử dụng phương thức Full configuration thay vì Easy create để chủ động cấu hình các thông số cơ sở dữ liệu.<br> - Lựa chọn MySQL làm Database Engine theo hướng dẫn Workshop.<br> - Chọn Production template và lựa chọn Multi-AZ DB instance deployment (2 instances) nhằm tìm hiểu khả năng triển khai cơ sở dữ liệu có tính sẵn sàng cao.<br> - Đặt DB Instance Identifier là `db-instance`, Master Username là `admin` và lựa chọn Self managed trong phần Credential Management.<br> - Thiết lập mật khẩu quản trị theo yêu cầu cấu hình của Workshop, xác nhận mật khẩu và lưu giữ thông tin xác thực an toàn để phục vụ những bước kết nối tiếp theo.<br> - Cấu hình Instance Class là `db.m5.large`, Storage Type là General Purpose SSD (gp3) và Allocated Storage là 20 GiB theo hướng dẫn Workshop.<br> - Trong phần Connectivity, lựa chọn Don't connect to an EC2 compute resource, sử dụng VPC đã tạo và DB Subnet Group `rds-subnet-group`.<br> - Cấu hình Public Access là No để không cho phép cơ sở dữ liệu truy cập công khai từ Internet.<br> - Trong phần VPC Security Group, lựa chọn Choose existing và gắn Security Group `rds-sg` vào DB Instance.<br> - Trong phần Additional Configuration, thiết lập Initial Database Name là `fcaj`, giữ các tùy chọn còn lại theo mặc định và hoàn tất quá trình tạo cơ sở dữ liệu.<br> - Kiểm tra trạng thái tạo RDS Database Instance và xác nhận Database Instance hoạt động sau khi quá trình khởi tạo hoàn tất.<br> - Truy cập Connectivity & security, lựa chọn Endpoints để tìm hiểu DB Endpoint và Port được sử dụng khi kết nối từ ứng dụng đến cơ sở dữ liệu.<br> - Tìm hiểu cách xem Logs & events để theo dõi các sự kiện, thông tin hoạt động và nhật ký liên quan đến vòng đời DB Instance.<br> - Truy cập Maintenance & backups để tìm hiểu lịch bảo trì, các bản cập nhật đang chờ xử lý và thông tin sao lưu của cơ sở dữ liệu. | 17/11/2026 | 17/11/2026 | [Get Started with Amazon RDS](https://000005.awsfcaj.com/)<br>[Create Security Group](https://000005.awsfcaj.com/2-prerequiste/2.2-create-ec2-sg/)<br>[Create Database Subnet Group](https://000005.awsfcaj.com/2-prerequiste/2.3-create-rds-subnet-group/)<br>[Create RDS Database Instance](https://000005.awsfcaj.com/3-create-rds/) |
| 4 | **Thực hành khởi chạy Amazon EC2 Instance và kết nối đến máy chủ Linux bằng SSH**<br><br> - Tìm hiểu tổng quan về Amazon EC2 và vai trò của dịch vụ trong việc cung cấp năng lực tính toán linh hoạt trên AWS Cloud để triển khai máy chủ ứng dụng.<br> - Truy cập Amazon EC2 Console và lựa chọn Launch instances để tạo máy chủ Linux phục vụ kết nối đến Amazon RDS.<br> - Đặt tên EC2 Instance là `ec2-instance` và lựa chọn hệ điều hành Amazon Linux 2023 AMI trong mục Quick Start.<br> - Cấu hình Instance Type là `t3.micro` theo hướng dẫn Workshop và tìm hiểu ý nghĩa của việc lựa chọn Instance Type phù hợp với nhu cầu xử lý của ứng dụng.<br> - Thực hành tạo Key Pair mới có tên `kp-linux`, lựa chọn Key Pair Type là RSA và Private Key Format là `.pem`.<br> - Tải tệp private key `kp-linux.pem` về máy tính cá nhân và lưu giữ an toàn để sử dụng trong quá trình kết nối SSH.<br> - Trong phần Network Settings, lựa chọn VPC đã tạo ở bước trước và Public Subnet.<br> - Bật Auto-assign public IP để EC2 Instance được cấp địa chỉ Public IPv4 phục vụ kết nối từ máy tính cá nhân.<br> - Lựa chọn Select existing security group và gắn Security Group `ec2-sg` vào EC2 Instance.<br> - Kiểm tra lại AMI, Instance Type, Key Pair, VPC, Subnet và Security Group trước khi lựa chọn Launch instance.<br> - Theo dõi quá trình khởi tạo EC2 Instance, đợi trạng thái chuyển sang Running và kiểm tra các Status Checks trước khi thực hiện kết nối.<br> - Sao chép địa chỉ Public IPv4 của `ec2-instance` từ giao diện EC2 Console.<br> - Thực hành kết nối đến Amazon Linux 2023 thông qua SSH bằng phần mềm MobaXterm trên máy tính Windows.<br> - Tạo New Session, lựa chọn SSH và cấu hình Remote Host bằng địa chỉ Public IPv4 của EC2 Instance.<br> - Thiết lập username là `ec2-user`, Port là 22, mở Advanced SSH settings và lựa chọn Use private key để chỉ định tệp `kp-linux.pem` đã tải về.<br> - Xác nhận kết nối SSH và hoàn tất quá trình đăng nhập vào máy chủ Amazon Linux 2023.<br> - Kiểm tra môi trường Terminal trên EC2 Instance và làm quen với thao tác quản trị máy chủ Linux thông qua dòng lệnh.<br> - Hiểu được vai trò của Public Subnet, Public IPv4, Key Pair và Security Group trong quá trình thiết lập kết nối đến EC2 Instance.<br> - Nhận thức được tầm quan trọng của việc bảo vệ private key và giới hạn nguồn truy cập SSH vào các địa chỉ IP đáng tin cậy nhằm tăng cường bảo mật máy chủ. | 18/11/2026 | 18/11/2026 | [Get Started with Amazon RDS](https://000005.awsfcaj.com/)<br>[Launch EC2 Instance](https://000005.awsfcaj.com/4-create-ec2/) |
| 5 | **Thực hành kết nối EC2 với Amazon RDS MySQL và triển khai ứng dụng AWS User Management**<br><br> - Tìm hiểu mô hình kết nối giữa Amazon EC2 và Amazon RDS, trong đó EC2 đóng vai trò máy chủ triển khai ứng dụng còn RDS đảm nhiệm việc lưu trữ và quản lý dữ liệu quan hệ.<br> - Thực hành cập nhật các gói phần mềm trên Amazon Linux 2023 bằng lệnh `sudo dnf update -y` trước khi chuẩn bị môi trường triển khai ứng dụng.<br> - Cài đặt Git bằng lệnh `sudo yum install git` và cài đặt MySQL Command Line Client thông qua gói `mariadb105` bằng lệnh `sudo dnf install mariadb105`.<br> - Kiểm tra phiên bản Git và MariaDB Client sau khi cài đặt bằng lệnh `git --version && mariadb --version`.<br> - Truy cập Amazon RDS, mở DB Instance `db-instance` và sao chép DB Endpoint trong mục Connectivity & security → Endpoints.<br> - Thực hành kết nối đến cơ sở dữ liệu thông qua MySQL Command Line Client bằng lệnh `mysql -h [YOUR-RDS-ENDPOINT] -P 3306 -u admin -p`, thay thế Endpoint bằng thông tin thực tế và nhập mật khẩu Master User đã cấu hình.<br> - Tìm hiểu vai trò của các tham số kết nối MySQL, bao gồm `-h` là DB Endpoint, `-P` là Port 3306 và `-u` là tài khoản quản trị cơ sở dữ liệu.<br> - Sử dụng câu lệnh SQL `SHOW DATABASES;` để kiểm tra danh sách cơ sở dữ liệu hiện có trong RDS.<br> - Kiểm tra sự tồn tại của cơ sở dữ liệu `fcaj`; sử dụng `CREATE DATABASE IF NOT EXISTS fcaj;` nếu cơ sở dữ liệu chưa tồn tại.<br> - Sử dụng câu lệnh `USE fcaj;` để lựa chọn cơ sở dữ liệu phục vụ các thao tác tiếp theo.<br> - Thực hành tạo bảng `user` trong cơ sở dữ liệu `fcaj` bằng câu lệnh SQL CREATE TABLE.<br> - Tìm hiểu cấu trúc bảng `user`, bao gồm các trường `id`, `first_name`, `last_name`, `email`, `phone`, `comments` và `status`.<br> - Tìm hiểu cách khai báo Primary Key, thuộc tính AUTO_INCREMENT, ràng buộc UNIQUE cho trường email và giá trị mặc định `active` cho trường status.<br> - Thực hành sử dụng câu lệnh INSERT INTO để thêm các bản ghi dữ liệu mẫu vào bảng `user` theo hướng dẫn Workshop.<br> - Sử dụng câu lệnh `SELECT * FROM user;` để truy vấn và kiểm tra toàn bộ dữ liệu đã được lưu trong bảng.<br> - Tìm hiểu thêm một số câu lệnh SQL phục vụ quản lý và kiểm tra cơ sở dữ liệu:<br>&nbsp;&nbsp;+ `USE database_name;`: Chuyển sang cơ sở dữ liệu được chỉ định.<br>&nbsp;&nbsp;+ `DESCRIBE table_name;`: Hiển thị cấu trúc của bảng, bao gồm tên cột, kiểu dữ liệu và các thuộc tính liên quan.<br>&nbsp;&nbsp;+ Truy vấn bảng `information_schema.tables` để kiểm tra dung lượng cơ sở dữ liệu dựa trên tổng kích thước dữ liệu và chỉ mục.<br> - Thực hành triển khai ứng dụng AWS User Management bằng Node.js trên EC2 thông qua việc tải mã nguồn từ GitHub bằng lệnh `git clone https://github.com/thienluhoan/000006-EC2.git`.<br> - Di chuyển vào thư mục dự án bằng lệnh `cd 000006-EC2` và kiểm tra các tệp mã nguồn phục vụ triển khai ứng dụng.<br> - Tạo và cấu hình file `.env` bằng trình soạn thảo `nano .env` để khai báo các biến môi trường kết nối cơ sở dữ liệu, bao gồm DB_HOST, DB_NAME (`fcaj`), DB_USER (`admin`) và DB_PASS.<br> - Thay thế DB_HOST bằng DB Endpoint thực tế của RDS và sử dụng thông tin xác thực đã thiết lập khi tạo Database Instance.<br> - Tìm hiểu Bash Script và thực hành tạo file `script.sh` bằng lệnh `nano script.sh` để tự động hóa quá trình chuẩn bị môi trường triển khai Node.js trên Amazon Linux 2023.<br> - Tìm hiểu và thực hành sử dụng NVM (Node Version Manager) thông qua Bash Script để cài đặt Node.js LTS, lựa chọn phiên bản mặc định và kiểm tra phiên bản Node.js, NPM sau khi cài đặt.<br> - Thực hành cài đặt PM2 trên phạm vi toàn hệ thống thông qua NPM để quản lý và giám sát tiến trình chạy ứng dụng Node.js.<br> - Thực hành khởi tạo `package.json` bằng `npm init -y` khi tệp chưa tồn tại và cài đặt các thư viện cần thiết:<br>&nbsp;&nbsp;+ Express.<br>&nbsp;&nbsp;+ dotenv.<br>&nbsp;&nbsp;+ express-handlebars.<br>&nbsp;&nbsp;+ body-parser.<br>&nbsp;&nbsp;+ mysql.<br>&nbsp;&nbsp;+ Nodemon (Development Dependency).<br> - Tìm hiểu cách cấu hình các NPM Scripts trong `package.json` bằng lệnh `npm pkg set`, bao gồm `start` sử dụng PM2 để chạy ứng dụng và `dev` sử dụng Nodemon phục vụ quá trình phát triển.<br> - Thực hành cấu hình PM2 khởi động cùng hệ thống Linux thông qua systemd để hỗ trợ quản lý tiến trình ứng dụng sau khi máy chủ khởi động lại.<br> - Cấp quyền thực thi cho Bash Script bằng lệnh `chmod +x script.sh` và chạy `bash script.sh` để bắt đầu quá trình cài đặt và cấu hình môi trường.<br> - Sử dụng lệnh `source ~/.bashrc` để tải lại các thiết lập môi trường Terminal sau khi cài đặt Node.js bằng NVM.<br> - Khởi chạy ứng dụng thông qua lệnh `npm start`, sử dụng `pm2 save` để lưu danh sách tiến trình và `pm2 status` để kiểm tra trạng thái hoạt động của ứng dụng.<br> - Quay lại EC2 Console, sao chép Public IPv4 của `ec2-instance` và truy cập ứng dụng thông qua trình duyệt bằng đường dẫn `http://<EC2-Public-IP>:5000`.<br> - Kiểm tra giao diện AWS User Management trên trình duyệt và xác nhận khả năng hoạt động của ứng dụng được triển khai trên EC2 và kết nối đến cơ sở dữ liệu Amazon RDS.<br> - Hiểu được quy trình kết hợp EC2, RDS, VPC và Security Groups để xây dựng hệ thống ứng dụng Web có khả năng tách biệt máy chủ ứng dụng với máy chủ cơ sở dữ liệu. | 19/11/2026 | 19/11/2026 | [Get Started with Amazon RDS](https://000005.awsfcaj.com/)<br>[Application Deployment](https://000005.awsfcaj.com/5-deploy-app/) |
| 6 | **Tìm hiểu và thực hành sao lưu, khôi phục Amazon RDS và dọn dẹp tài nguyên sau Workshop**<br><br> - Tìm hiểu vai trò của chức năng Backup and Restore trong Amazon RDS, hỗ trợ bảo vệ dữ liệu, khôi phục cơ sở dữ liệu và duy trì tính liên tục của hệ thống khi xảy ra sự cố.<br> - Phân biệt Automated Backups và Manual DB Snapshots:<br>&nbsp;&nbsp;+ **Automated Backups:** Các bản sao lưu tự động được Amazon RDS quản lý, hỗ trợ khôi phục dữ liệu về một thời điểm trong khoảng thời gian lưu trữ được cấu hình.<br>&nbsp;&nbsp;+ **Manual DB Snapshots:** Các bản sao lưu được người dùng chủ động tạo, có thể được lưu giữ cho đến khi người dùng thực hiện xóa.<br> - Tìm hiểu cơ chế Point-in-Time Recovery của Automated Backups và khả năng khôi phục dữ liệu về một thời điểm phù hợp trong thời gian lưu trữ.<br> - Thực hành truy cập AWS RDS Console, lựa chọn Databases và mở DB Instance đã tạo trước đó.<br> - Truy cập tab Maintenance & backups để kiểm tra trạng thái sao lưu, thời gian lưu trữ, thời điểm khôi phục gần nhất và các thông tin liên quan đến quá trình bảo trì cơ sở dữ liệu.<br> - Tìm hiểu danh sách các Database Snapshots được lưu trữ trong phần Snapshots và vai trò của từng Snapshot trong quá trình bảo vệ dữ liệu.<br> - Thực hành lựa chọn một DB Snapshot cần khôi phục và sử dụng chức năng Restore để tạo một Database Instance mới từ Snapshot đã chọn.<br> - Đặt DB Instance Identifier cho cơ sở dữ liệu được khôi phục là `fcaj-2` theo hướng dẫn Workshop.<br> - Kiểm tra và cấu hình lại các thông số của Database Instance mới, bao gồm tài nguyên tính toán, lưu trữ, VPC, Subnet và Security Groups phù hợp.<br> - Giữ các cấu hình còn lại theo hướng dẫn, lựa chọn Restore DB instance để bắt đầu quá trình khôi phục cơ sở dữ liệu.<br> - Theo dõi trạng thái tạo DB Instance `fcaj-2` trên giao diện Amazon RDS và chờ quá trình Restore hoàn tất.<br> - Kiểm tra sự xuất hiện của Database Instance mới trong danh sách Databases và tìm hiểu DB Endpoint riêng được tạo sau khi khôi phục.<br> - Tìm hiểu rằng quá trình Restore từ Snapshot tạo ra một DB Instance hoàn toàn mới với Endpoint riêng, do đó ứng dụng cần cập nhật chuỗi kết nối nếu muốn chuyển sang sử dụng cơ sở dữ liệu được khôi phục.<br> - Tìm hiểu cách xác minh khả năng kết nối và tính toàn vẹn dữ liệu sau khi khôi phục; kiểm tra Security Groups và các cấu hình liên quan để đảm bảo quyền truy cập phù hợp.<br> - Tổng hợp các nội dung đã thực hành về Amazon RDS, bao gồm tạo Database Instance, kết nối từ EC2, triển khai ứng dụng Node.js và sao lưu, khôi phục dữ liệu.<br> - Thực hành dọn dẹp EC2 Instance bằng cách truy cập EC2 Console → Instances, lựa chọn `ec2-instance`, mở Instance state và chọn Terminate (delete) instance theo hướng dẫn Workshop.<br> - Truy cập Amazon RDS, lựa chọn Database Instance `db-instance` và sử dụng Modify để tắt Enable deletion protection trước khi xóa cơ sở dữ liệu.<br> - Chọn Apply immediately để áp dụng thay đổi, sau đó truy cập Actions → Delete để thực hiện xóa Database Instance.<br> - Trong hộp thoại xác nhận, lựa chọn I acknowledge that upon instance deletion, automated backups, including system snapshots and point-in-time recovery, will no longer be available; nhập `delete me` và xác nhận Delete.<br> - Thực hiện quy trình tương tự để xóa Database Instance `fcaj-2` sau khi đã kiểm tra nhu cầu lưu giữ dữ liệu.<br> - Hiểu được việc xóa RDS Database Instance có thể xóa các bản sao lưu tự động và dữ liệu liên quan; cần tạo Final Snapshot trước khi xóa nếu có yêu cầu bảo toàn dữ liệu.<br> - Chờ quá trình xóa Database Instance hoàn tất trước khi tiến hành xóa DB Subnet Group `rds-subnet-group` trong mục Subnet groups của Amazon RDS.<br> - Truy cập Amazon VPC, mở mục Internet gateways, lựa chọn Internet Gateway `rds-igw` và thực hiện Actions → Detach from VPC để tách Internet Gateway khỏi VPC.<br> - Truy cập Your VPCs, lựa chọn VPC `rds-vpc` và thực hiện Actions → Delete VPC theo hướng dẫn Workshop.<br> - Kiểm tra các tài nguyên liên quan sau khi dọn dẹp, đặc biệt là EBS Snapshots và CloudWatch Logs có thể vẫn tồn tại nếu chưa được xóa riêng.<br> - Truy cập AWS Billing Dashboard để kiểm tra các khoản chi phí còn phát sinh từ tài nguyên của Workshop và xác nhận không còn tài nguyên thử nghiệm không cần thiết. | 20/11/2026 | 20/11/2026 | [Get Started with Amazon RDS](https://000005.awsfcaj.com/)<br>[Backup and Restore](https://000005.awsfcaj.com/6-backup/)<br>[Clean Up Resources](https://000005.awsfcaj.com/7-cleanup/) |

### Kết quả đạt được trong tuần 7:

- Nắm được tổng quan về Amazon Relational Database Service (Amazon RDS), hiểu được đây là dịch vụ cơ sở dữ liệu quan hệ được AWS quản lý, hỗ trợ triển khai, vận hành, sao lưu, cập nhật và mở rộng cơ sở dữ liệu trên AWS Cloud.

- Hiểu được vai trò của Amazon RDS đối với các ứng dụng sử dụng cơ sở dữ liệu quan hệ, đặc biệt là các hệ thống lưu trữ dữ liệu có cấu trúc, sử dụng SQL và xử lý giao dịch trực tuyến (OLTP).

- Nhận biết được các hệ quản trị cơ sở dữ liệu được Amazon RDS hỗ trợ, bao gồm:
  - Amazon Aurora.
  - MySQL.
  - MariaDB.
  - Oracle.
  - Microsoft SQL Server.
  - PostgreSQL.

- Phân biệt được Amazon RDS với phương pháp tự triển khai Database trên EC2, đặc biệt về trách nhiệm quản lý hệ điều hành, cập nhật phần mềm, sao lưu, bảo mật và mở rộng tài nguyên.

- Nắm được các tính năng quản lý quan trọng của Amazon RDS:
  - Automated Backups và Manual Snapshots.
  - Database Software Updates và Maintenance Windows.
  - Multi-AZ Deployment.
  - Read Replicas.
  - Database Endpoint.
  - Storage Scaling và Compute Scaling.
  - Encryption và Security Management.

- Hiểu được các tùy chọn lưu trữ của Amazon RDS:
  - **General Purpose SSD (gp3/gp2):** Phù hợp với phần lớn khối lượng công việc cơ sở dữ liệu thông thường, cung cấp hiệu năng với chi phí hợp lý.
  - **Provisioned IOPS SSD (io1/io2):** Phù hợp với các ứng dụng cơ sở dữ liệu yêu cầu hiệu năng đọc ghi cao và ổn định.
  - **Magnetic Storage:** Tùy chọn lưu trữ cũ với hiệu năng hạn chế, không được khuyến nghị cho các triển khai mới.

- Hiểu được các cơ chế High Availability và Disaster Recovery của Amazon RDS:
  - **Multi-AZ Deployments:** Sử dụng Standby Replica tại Availability Zone khác, sao chép dữ liệu đồng bộ và hỗ trợ tự động chuyển đổi dự phòng khi DB Instance chính gặp sự cố.
  - **Read Replicas:** Sử dụng cơ chế sao chép bất đồng bộ để hỗ trợ mở rộng khả năng đọc dữ liệu và một số trường hợp khôi phục sau sự cố.
  - **Global Databases:** Hỗ trợ sao chép dữ liệu giữa các AWS Region nhằm cải thiện khả năng truy cập dữ liệu và Disaster Recovery.

- Nắm được các phương thức bảo mật Amazon RDS, bao gồm mã hóa dữ liệu khi lưu trữ thông qua AWS KMS, mã hóa dữ liệu khi truyền bằng SSL/TLS, cô lập mạng bằng VPC và kiểm soát quyền truy cập bằng IAM Policies.

- Hiểu được vai trò của DB Instance và DB Endpoint trong Amazon RDS, biết cách tìm thông tin kết nối cơ sở dữ liệu thông qua AWS Management Console.

- Có kinh nghiệm thực hành tạo Amazon VPC phục vụ triển khai RDS, cấu hình IPv4 CIDR Block `10.0.0.0/16`, lựa chọn Default Tenancy và thiết lập kiến trúc mạng phù hợp.

- Thực hành cấu hình môi trường mạng gồm:
  - 2 Availability Zones.
  - 2 Public Subnets.
  - 2 Private Subnets.
  - Không tạo NAT Gateway và VPC Endpoint trong bài thực hành nhằm hạn chế chi phí phát sinh.

- Hiểu được cách cấu hình tự động cấp phát Public IPv4 cho Public Subnets và nhận thức được tầm quan trọng của việc không cấp phát Public IPv4 cho các Subnets dành riêng cho cơ sở dữ liệu RDS.

- Có kinh nghiệm thực hành tạo và cấu hình hai Security Groups riêng biệt:
  - **ec2-sg:** Quản lý kết nối đến EC2 Instance thông qua SSH (22), HTTP (80), HTTPS (443) và Custom TCP (5000).
  - **rds-sg:** Kiểm soát kết nối đến RDS MySQL thông qua cổng 3306, chỉ cho phép nguồn truy cập từ Security Group `ec2-sg`.

- Hiểu được lợi ích của việc sử dụng Security Group riêng biệt cho EC2 và RDS, giúp tăng cường khả năng cô lập tài nguyên và kiểm soát kết nối giữa máy chủ ứng dụng với cơ sở dữ liệu.

- Nắm được cách tạo DB Subnet Group với tên `rds-subnet-group`, lựa chọn Subnets thuộc ít nhất hai Availability Zones và ưu tiên sử dụng Private Subnets để tăng cường bảo mật cho cơ sở dữ liệu.

- Có kinh nghiệm thực hành khởi tạo Amazon RDS Database Instance bằng phương thức Full configuration, lựa chọn MySQL làm Database Engine và cấu hình các thông số theo hướng dẫn Workshop.

- Nắm được các thông số cấu hình quan trọng của DB Instance:
  - DB Instance Identifier: `db-instance`.
  - Master Username: `admin`.
  - Credential Management: Self managed.
  - Instance Class: `db.m5.large`.
  - Storage Type: General Purpose SSD (gp3).
  - Allocated Storage: 20 GiB.
  - Initial Database Name: `fcaj`.
  - Public Access: No.
  - VPC Security Group: `rds-sg`.
  - DB Subnet Group: `rds-subnet-group`.
  - Deployment: Multi-AZ DB instance deployment (2 instances).

- Hiểu được lợi ích của việc lựa chọn Multi-AZ DB instance deployment trong việc tăng cường tính sẵn sàng, sử dụng cơ chế sao chép đồng bộ và hỗ trợ tự động chuyển đổi dự phòng khi xảy ra sự cố.

- Biết cách kiểm tra DB Endpoint, Port và các thông tin kết nối trong mục Connectivity & security của RDS Database Instance.

- Hiểu được cách theo dõi thông tin hoạt động của Amazon RDS thông qua Log & events, bao gồm CloudWatch Alarms, Recent Events và các tệp nhật ký kỹ thuật.

- Nắm được cách kiểm tra Maintenance & backups để theo dõi lịch bảo trì, các cập nhật đang chờ xử lý, trạng thái sao lưu và các Database Snapshots.

- Có kinh nghiệm thực hành khởi chạy Amazon EC2 Instance sử dụng Amazon Linux 2023, lựa chọn Instance Type `t3.micro`, tạo Key Pair `kp-linux` định dạng `.pem` và cấu hình VPC, Public Subnet, Public IPv4 cùng Security Group phù hợp.

- Thực hành kết nối đến EC2 Instance thông qua SSH bằng MobaXterm, sử dụng Public IPv4, username `ec2-user`, port 22 và private key đã tạo.

- Hiểu được vai trò của Key Pair, Public IP và Security Group trong quá trình thiết lập kết nối từ máy tính cá nhân đến EC2 Instance; nhận thức được tầm quan trọng của việc bảo vệ private key và giới hạn nguồn truy cập SSH.

- Nắm được cách chuẩn bị môi trường Amazon Linux 2023 bằng việc cập nhật các gói hệ thống, cài đặt Git và MariaDB Client thông qua các lệnh:
  - `sudo dnf update -y`
  - `sudo yum install git`
  - `sudo dnf install mariadb105`
  - `git --version && mariadb --version`

- Có kinh nghiệm thực hành kết nối từ EC2 đến Amazon RDS MySQL bằng MySQL Command Line Client, sử dụng DB Endpoint, Port 3306, Master Username và Password đã cấu hình.

- Hiểu được chức năng của các câu lệnh SQL cơ bản phục vụ quản lý cơ sở dữ liệu:
  - `SHOW DATABASES;`: Hiển thị danh sách các cơ sở dữ liệu.
  - `CREATE DATABASE IF NOT EXISTS fcaj;`: Tạo cơ sở dữ liệu nếu chưa tồn tại.
  - `USE fcaj;`: Lựa chọn cơ sở dữ liệu cần thao tác.
  - `CREATE TABLE`: Tạo bảng và thiết lập cấu trúc dữ liệu.
  - `INSERT INTO`: Thêm dữ liệu vào bảng.
  - `SELECT * FROM user;`: Truy vấn toàn bộ dữ liệu trong bảng.

- Thực hành tạo bảng `user` trong cơ sở dữ liệu `fcaj`, bao gồm các trường dữ liệu:
  - `id`: Khóa chính, sử dụng AUTO_INCREMENT.
  - `first_name`: Tên.
  - `last_name`: Họ.
  - `email`: Địa chỉ email, có ràng buộc UNIQUE.
  - `phone`: Số điện thoại.
  - `comments`: Nội dung ghi chú.
  - `status`: Trạng thái người dùng, sử dụng ENUM với giá trị `active` hoặc `inactive` và giá trị mặc định `active`.

- Có kinh nghiệm thực hành thêm các bản ghi dữ liệu mẫu vào bảng `user` và sử dụng câu lệnh SELECT để kiểm tra danh sách dữ liệu đã được lưu trong Amazon RDS MySQL.

- Nắm được một số câu lệnh SQL mở rộng để kiểm tra cấu trúc và dung lượng cơ sở dữ liệu, bao gồm `DESCRIBE table_name` và truy vấn thông tin từ `information_schema.tables`.

- Thực hành tải mã nguồn ứng dụng AWS User Management từ GitHub bằng lệnh `git clone https://github.com/thienluhoan/000006-EC2.git` và chuẩn bị thư mục dự án để triển khai trên Amazon EC2.

- Hiểu được vai trò của file `.env` trong việc quản lý thông tin cấu hình ứng dụng và kết nối đến cơ sở dữ liệu Amazon RDS, bao gồm DB_HOST, DB_NAME, DB_USER và DB_PASS.

- Có kinh nghiệm sử dụng NVM (Node Version Manager) để cài đặt Node.js LTS, thiết lập phiên bản mặc định và kiểm tra phiên bản Node.js, NPM sau khi cài đặt.

- Thực hành sử dụng Bash Script để tự động hóa quá trình chuẩn bị môi trường triển khai ứng dụng Node.js trên Amazon Linux 2023.

- Nắm được cách cài đặt các thành phần phục vụ ứng dụng:
  - PM2 để quản lý tiến trình Node.js.
  - Express để xây dựng ứng dụng Web.
  - dotenv để quản lý biến môi trường.
  - express-handlebars để sử dụng giao diện Handlebars.
  - body-parser để xử lý dữ liệu gửi từ Request Body.
  - mysql để kết nối cơ sở dữ liệu MySQL.
  - Nodemon để hỗ trợ quá trình phát triển ứng dụng.

- Hiểu được cách cấu hình NPM Scripts trong `package.json`, sử dụng PM2 để khởi chạy ứng dụng và Nodemon để chạy ứng dụng trong môi trường Development.

- Thực hành cấp quyền thực thi cho Bash Script bằng `chmod +x script.sh`, chạy script bằng `bash script.sh` và cập nhật lại môi trường Terminal bằng `source ~/.bashrc`.

- Có kinh nghiệm khởi chạy và quản lý ứng dụng Node.js bằng các lệnh:
  - `npm start`: Khởi chạy ứng dụng thông qua PM2.
  - `pm2 save`: Lưu danh sách tiến trình để hỗ trợ khôi phục sau khi máy chủ khởi động lại.
  - `pm2 status`: Kiểm tra trạng thái, mức sử dụng CPU, bộ nhớ và số lần khởi động lại của các tiến trình ứng dụng.

- Hiểu được cách thiết lập PM2 khởi động cùng hệ thống Linux thông qua systemd nhằm hỗ trợ duy trì hoạt động của ứng dụng sau khi EC2 Instance khởi động lại.

- Thực hành truy cập ứng dụng AWS User Management thông qua Public IPv4 của EC2 kết hợp cổng 5000 và kiểm tra giao diện ứng dụng trên trình duyệt.

- Hiểu được kiến trúc triển khai ứng dụng trên AWS, trong đó:
  - Amazon EC2 đảm nhiệm vai trò máy chủ ứng dụng.
  - Amazon RDS đảm nhiệm vai trò máy chủ cơ sở dữ liệu.
  - Amazon VPC cung cấp môi trường mạng cô lập cho các tài nguyên.
  - Security Groups kiểm soát quyền truy cập giữa EC2 và RDS.
  - DB Endpoint hỗ trợ thiết lập kết nối giữa ứng dụng và cơ sở dữ liệu.

- Nắm được vai trò của Automated Backups và Manual DB Snapshots trong việc bảo vệ dữ liệu, hỗ trợ khôi phục cơ sở dữ liệu và duy trì tính liên tục của hệ thống.

- Phân biệt được hai phương thức sao lưu:
  - **Automated Backups:** Được Amazon RDS quản lý tự động, hỗ trợ Point-in-Time Recovery trong khoảng thời gian lưu trữ được cấu hình.
  - **Manual DB Snapshots:** Được người dùng chủ động tạo và tiếp tục được lưu giữ cho đến khi thực hiện xóa.

- Thực hành kiểm tra trạng thái sao lưu trong mục Maintenance & backups, tìm hiểu cách quản lý Database Snapshots và thực hiện Restore từ Snapshot để tạo một DB Instance mới có tên `fcaj-2`.

- Hiểu được quá trình Restore từ Snapshot tạo ra một Database Instance mới với Endpoint riêng, đồng thời nhận thức được cần cập nhật chuỗi kết nối của ứng dụng khi chuyển sang sử dụng cơ sở dữ liệu được khôi phục.

- Nắm được các bước kiểm tra tính toàn vẹn dữ liệu, khả năng kết nối và cấu hình Security Groups sau khi khôi phục Database Instance.

- Có kiến thức về quy trình dọn dẹp tài nguyên sau Workshop, bao gồm:
  - Terminate EC2 Instance `ec2-instance`.
  - Tắt Deletion Protection trước khi xóa RDS Database Instance.
  - Xác nhận xóa `db-instance` và `fcaj-2`.
  - Xóa DB Subnet Group `rds-subnet-group` sau khi quá trình xóa Database Instance hoàn tất.
  - Detach Internet Gateway `rds-igw` khỏi VPC.
  - Xóa VPC `rds-vpc`.
  - Kiểm tra các EBS Snapshots và CloudWatch Logs còn tồn tại nếu chưa được xóa riêng.

- Nhận thức được tầm quan trọng của việc tạo Final Snapshot trước khi xóa cơ sở dữ liệu nếu cần bảo toàn dữ liệu; hiểu được rằng việc xóa Database Instance có thể làm mất các Automated Backups và khả năng Point-in-Time Recovery liên quan.

- Hiểu được tầm quan trọng của việc kiểm tra AWS Billing Dashboard sau khi hoàn thành Workshop nhằm phát hiện các tài nguyên còn tồn tại và hạn chế chi phí phát sinh ngoài dự kiến.

- Tổng hợp được kiến thức và kinh nghiệm thực hành về Amazon RDS trong việc xây dựng môi trường mạng, triển khai cơ sở dữ liệu MySQL, kết nối ứng dụng từ EC2, triển khai ứng dụng Node.js, sao lưu và khôi phục dữ liệu trên AWS Cloud.
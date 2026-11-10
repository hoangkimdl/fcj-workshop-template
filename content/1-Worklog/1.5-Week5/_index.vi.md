---
title: "Worklog Tuần 5"
date: 2026-11-02
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

- Tìm hiểu tổng quan về AWS CloudShell, vai trò và lợi ích của môi trường dòng lệnh được AWS quản lý trực tiếp trên trình duyệt.
- Nắm được cách truy cập AWS CloudShell thông qua AWS Management Console, khởi tạo CloudShell Environment và làm quen với giao diện Terminal.
- Tìm hiểu các lệnh Linux cơ bản thường được sử dụng trong AWS CloudShell để quản lý thư mục, tệp tin và kiểm tra quyền truy cập.
- Thực hành sử dụng các lệnh `pwd`, `ls -la`, `mkdir`, `cd`, `touch`, `vi` và `cat` để thao tác với thư mục và tệp tin trong môi trường CloudShell.
- Tìm hiểu AWS Command Line Interface (AWS CLI), chức năng và khả năng quản lý các dịch vụ AWS thông qua dòng lệnh.
- Thực hành sử dụng AWS CLI để kiểm tra phiên bản công cụ, liệt kê các Amazon S3 Bucket và truy vấn thông tin EC2 Instance trong tài khoản AWS.
- Nắm được cách tải tệp từ máy tính cá nhân lên CloudShell và tải tệp từ CloudShell về máy tính thông qua giao diện quản lý tệp.
- Hiểu được cách quản lý và xóa CloudShell Environment sau khi hoàn thành bài thực hành nhằm hạn chế việc lưu trữ dữ liệu không cần thiết.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | **Tìm hiểu AWS CloudShell và khởi tạo CloudShell Environment**<br><br> - Tìm hiểu tổng quan về AWS CloudShell, một môi trường dòng lệnh được AWS quản lý hoàn toàn và có thể truy cập trực tiếp thông qua trình duyệt web.<br> - Tìm hiểu vai trò của CloudShell trong việc thực hiện các thao tác quản lý tài nguyên AWS mà không cần cài đặt hoặc cấu hình môi trường dòng lệnh trên máy tính cá nhân.<br> - Tìm hiểu các công cụ được tích hợp sẵn trong CloudShell, bao gồm AWS CLI, AWS SDKs và một số công cụ dòng lệnh cần thiết.<br> - Tìm hiểu cơ chế xác thực của CloudShell thông qua quyền truy cập được kế thừa từ IAM User hoặc IAM Role đang sử dụng trong AWS Management Console.<br> - Tìm hiểu dung lượng lưu trữ được cấp phát sẵn trong thư mục `$HOME`, với 1 GB dung lượng lưu trữ được phân bổ cho môi trường CloudShell.<br> - Thực hành đăng nhập AWS Management Console bằng tài khoản AWS đã đăng ký.<br> - Sử dụng thanh tìm kiếm dịch vụ trên AWS Management Console, nhập từ khóa CloudShell và lựa chọn dịch vụ AWS CloudShell.<br> - Thực hành mở CloudShell Environment thông qua giao diện Terminal và lựa chọn tùy chọn mở môi trường `us-west-1` theo hướng dẫn Workshop.<br> - Làm quen với giao diện Terminal, khu vực nhập lệnh và cách tương tác với môi trường CloudShell.<br> - Kiểm tra khả năng truy cập CloudShell và chuẩn bị môi trường để thực hiện các bài thực hành tiếp theo. | 02/11/2026 | 02/11/2026 | [Getting Started with AWS CloudShell](https://000049.awsfcaj.com/) |
| 3 | **Tìm hiểu và thực hành các lệnh Linux cơ bản trong AWS CloudShell**<br><br> - Tìm hiểu vai trò của các lệnh Linux cơ bản trong việc quản lý thư mục, tệp tin và kiểm tra thông tin hệ thống thông qua giao diện dòng lệnh.<br> - Thực hành sử dụng lệnh `pwd` để hiển thị đường dẫn của thư mục làm việc hiện tại trong CloudShell.<br> - Thực hành sử dụng lệnh `ls -la` để liệt kê các tệp tin và thư mục, bao gồm cả những thành phần ẩn cùng thông tin quyền truy cập của người dùng và nhóm.<br> - Tìm hiểu ý nghĩa của các quyền truy cập `rwx`, bao gồm Read (đọc), Write (ghi) và Execute (thực thi).<br> - Phân biệt ba nhóm quyền truy cập tương ứng với User, Group và Other trong hệ thống Linux.<br> - Thực hành sử dụng lệnh `mkdir project` để tạo thư mục mới có tên `project`.<br> - Sử dụng lệnh `cd project` để di chuyển vào thư mục vừa tạo.<br> - Sử dụng lệnh `touch test.txt` để tạo tệp tin `test.txt` trong thư mục `project`.<br> - Thực hành sử dụng trình soạn thảo văn bản `vi test.txt` để chỉnh sửa nội dung tệp tin.<br> - Tìm hiểu thao tác nhấn phím `i` để chuyển sang chế độ Insert, nhập nội dung mẫu `Hello First Cloud AI Journey!`, sau đó nhấn `Esc` và sử dụng lệnh `:wq` để lưu nội dung và thoát khỏi trình soạn thảo.<br> - Sử dụng lệnh `cat test.txt` để hiển thị và kiểm tra nội dung đã lưu trong tệp tin.<br> - Kiểm tra lại cấu trúc thư mục và các tệp tin đã tạo trong quá trình thực hành. | 03/11/2026 | 03/11/2026 | [Getting Started with AWS CloudShell - Basic Commands](https://000049.awsfcaj.com/2-basicfeature/) |
| 4 | **Tìm hiểu và thực hành sử dụng AWS Command Line Interface (AWS CLI)**<br><br> - Tìm hiểu tổng quan về AWS Command Line Interface (AWS CLI), một công cụ cho phép quản lý và tương tác với nhiều dịch vụ AWS thông qua các lệnh trong Terminal.<br> - Tìm hiểu khả năng sử dụng AWS CLI để quản lý tài nguyên AWS, kiểm tra thông tin dịch vụ và tự động hóa các thao tác thông qua những tệp lệnh chứa nhiều câu lệnh liên tiếp.<br> - Tìm hiểu việc AWS CLI đã được cài đặt và cấu hình sẵn trong môi trường AWS CloudShell, không cần thực hiện cài đặt thủ công.<br> - Thực hành sử dụng lệnh `aws --version` để kiểm tra phiên bản AWS CLI hiện có trong CloudShell.<br> - Sử dụng lệnh `aws s3 ls` để liệt kê danh sách các Amazon S3 Bucket thuộc tài khoản AWS đang sử dụng.<br> - Sử dụng lệnh `aws ec2 describe-instances` để truy vấn và hiển thị thông tin các EC2 Instance trong tài khoản AWS.<br> - Tìm hiểu cách AWS CLI tương tác với các dịch vụ AWS dựa trên quyền truy cập của IAM User hoặc IAM Role hiện tại.<br> - Thực hành đọc kết quả trả về từ các câu lệnh AWS CLI và nhận biết thông tin cơ bản của các tài nguyên AWS.<br> - Hiểu được lợi ích của AWS CLI trong việc giảm thao tác trên giao diện quản lý AWS Console, hỗ trợ kiểm tra tài nguyên và thực hiện các công việc quản trị nhanh chóng. | 04/11/2026 | 04/11/2026 | [Getting Started with AWS CloudShell - Using AWS CLI](https://000049.awsfcaj.com/3-useawscli/) |
| 5 | **Thực hành tải lên và tải xuống tệp tin trong AWS CloudShell**<br><br> - Tìm hiểu chức năng quản lý tệp tin của AWS CloudShell và khả năng trao đổi dữ liệu giữa máy tính cá nhân với môi trường CloudShell.<br> - Thực hành tạo một tệp tin có tên `test.txt` trên máy tính cá nhân và nhập nội dung tùy ý để chuẩn bị cho quá trình tải lên.<br> - Truy cập giao diện AWS CloudShell, lựa chọn Actions → Upload file và chọn tệp `test.txt` từ máy tính cá nhân.<br> - Kiểm tra thông báo xác nhận tải tệp thành công sau khi hoàn tất thao tác Upload file.<br> - Sử dụng lệnh `ls` trong CloudShell để kiểm tra sự xuất hiện của tệp tin vừa tải lên.<br> - Sử dụng lệnh `cat test.txt` để đọc và kiểm tra nội dung của tệp tin đã được tải lên CloudShell.<br> - Thực hành tạo một tệp tin mới có tên `test1.txt` bằng lệnh `touch test1.txt` để chuẩn bị cho thao tác tải xuống.<br> - Sử dụng lệnh `vi test1.txt` để mở và chỉnh sửa tệp tin, nhập nội dung mẫu `Hello FCAJ!`, sau đó nhấn `Esc` và sử dụng `:wq` để lưu và thoát.<br> - Sử dụng lệnh `ls` để kiểm tra tên tệp tin vừa tạo trong môi trường CloudShell.<br> - Thực hành lựa chọn Actions → Download file, nhập tên tệp `test1.txt` và nhấn Download để tải tệp từ CloudShell về máy tính cá nhân.<br> - Mở tệp tin đã tải xuống trên máy tính và kiểm tra nội dung nhằm xác nhận quá trình tải xuống thành công.<br> - Hiểu được quy trình trao đổi tệp tin giữa máy tính cá nhân và AWS CloudShell phục vụ cho các bài thực hành quản trị tài nguyên AWS. | 05/11/2026 | 05/11/2026 | [Getting Started with AWS CloudShell - Using AWS CLI](https://000049.awsfcaj.com/3-useawscli/) |
| 6 | **Thực hành dọn dẹp và xóa CloudShell Environment sau Workshop**<br><br> - Tìm hiểu mục đích của việc dọn dẹp tài nguyên và dữ liệu CloudShell sau khi hoàn thành các bài thực hành.<br> - Kiểm tra lại môi trường CloudShell và các tệp tin đã tạo trong quá trình thực hành, bao gồm thư mục `project`, tệp `test.txt` và `test1.txt`.<br> - Thực hành truy cập mục Actions trên giao diện AWS CloudShell.<br> - Lựa chọn chức năng Delete để thực hiện xóa CloudShell Environment theo hướng dẫn Workshop.<br> - Xác nhận thao tác bằng cách nhấn Delete tại hộp thoại xác nhận xóa.<br> - Kiểm tra quá trình xóa CloudShell Environment và hoàn tất việc dọn dẹp môi trường thực hành.<br> - Tổng kết các nội dung đã thực hiện, bao gồm khởi tạo CloudShell, sử dụng lệnh Linux cơ bản, thao tác AWS CLI và quản lý tệp tin.<br> - Nhận thức được tầm quan trọng của việc kiểm tra và quản lý dữ liệu trong môi trường CloudShell sau khi hoàn thành Workshop. | 06/11/2026 | 06/11/2026 | [Getting Started with AWS CloudShell - Clean Up Resources](https://000049.awsfcaj.com/4-cleanup/) |

### Kết quả đạt được trong tuần 5:

- Nắm được tổng quan về AWS CloudShell, hiểu được vai trò của môi trường dòng lệnh được AWS quản lý hoàn toàn và khả năng truy cập trực tiếp thông qua AWS Management Console mà không cần cài đặt hoặc cấu hình công cụ trên máy tính cá nhân.

- Hiểu được những lợi ích chính của AWS CloudShell trong quá trình quản trị AWS, bao gồm:
  - Truy cập môi trường dòng lệnh trực tiếp trên trình duyệt.
  - Sử dụng AWS CLI và AWS SDKs được tích hợp sẵn.
  - Thực hiện các thao tác quản lý và kiểm tra tài nguyên AWS.
  - Hỗ trợ viết và thực thi các tập lệnh tự động hóa.
  - Cung cấp 1 GB dung lượng lưu trữ được phân bổ trong thư mục `$HOME`.

- Hiểu được cơ chế xác thực và cấp quyền truy cập của CloudShell thông qua IAM User hoặc IAM Role đang sử dụng trong AWS Management Console, giúp thực hiện các thao tác trên dịch vụ AWS theo quyền được cấp.

- Thực hành truy cập AWS CloudShell thông qua AWS Management Console, tìm kiếm dịch vụ CloudShell, mở CloudShell Environment và làm quen với giao diện Terminal.

- Nắm được cách sử dụng các lệnh Linux cơ bản trong AWS CloudShell, bao gồm:
  - **`pwd`:** Hiển thị đường dẫn của thư mục làm việc hiện tại.
  - **`ls -la`:** Liệt kê các tệp tin và thư mục, bao gồm các thành phần ẩn cùng thông tin quyền truy cập.
  - **`mkdir`:** Tạo thư mục mới.
  - **`cd`:** Di chuyển giữa các thư mục.
  - **`touch`:** Tạo tệp tin mới.
  - **`vi`:** Mở và chỉnh sửa nội dung tệp tin bằng trình soạn thảo văn bản.
  - **`cat`:** Hiển thị nội dung của tệp tin.

- Hiểu được ý nghĩa của các quyền truy cập Linux `rwx`, trong đó:
  - **Read (r):** Quyền đọc dữ liệu.
  - **Write (w):** Quyền ghi và chỉnh sửa dữ liệu.
  - **Execute (x):** Quyền thực thi.
  - **User:** Quyền của chủ sở hữu tệp tin hoặc thư mục.
  - **Group:** Quyền của nhóm người dùng.
  - **Other:** Quyền của những người dùng khác.

- Có kinh nghiệm thực hành tạo và quản lý thư mục, tệp tin trong CloudShell thông qua các thao tác:
  - Tạo thư mục `project` bằng lệnh `mkdir`.
  - Di chuyển vào thư mục bằng lệnh `cd`.
  - Tạo tệp `test.txt` bằng lệnh `touch`.
  - Chỉnh sửa nội dung bằng trình soạn thảo `vi`.
  - Lưu nội dung và thoát khỏi trình soạn thảo bằng tổ hợp thao tác `Esc` và `:wq`.
  - Kiểm tra nội dung tệp tin bằng lệnh `cat`.

- Nắm được tổng quan về AWS Command Line Interface (AWS CLI), hiểu được vai trò của công cụ trong việc quản lý, tương tác với các dịch vụ AWS thông qua dòng lệnh và hỗ trợ tự động hóa các thao tác quản trị.

- Hiểu được AWS CLI đã được cài đặt và cấu hình sẵn trong AWS CloudShell, không cần phải thực hiện các bước cài đặt thủ công.

- Thực hành sử dụng các lệnh AWS CLI để kiểm tra và truy vấn thông tin tài nguyên AWS, bao gồm:
  - **`aws --version`:** Kiểm tra phiên bản AWS CLI đang được sử dụng.
  - **`aws s3 ls`:** Liệt kê danh sách các Amazon S3 Bucket trong tài khoản AWS.
  - **`aws ec2 describe-instances`:** Truy vấn thông tin các EC2 Instance trong tài khoản AWS.

- Hiểu được cách AWS CLI sử dụng quyền truy cập được cấp cho IAM User hoặc IAM Role hiện tại để thực hiện các thao tác trên dịch vụ AWS.

- Có kinh nghiệm thực hành quản lý và trao đổi tệp tin giữa máy tính cá nhân với môi trường CloudShell, bao gồm:
  - Tạo tệp `test.txt` trên máy tính cá nhân để chuẩn bị tải lên CloudShell.
  - Sử dụng Actions → Upload file để tải tệp từ máy tính cá nhân lên CloudShell.
  - Sử dụng lệnh `ls` để kiểm tra tệp tin đã được tải lên.
  - Sử dụng lệnh `cat` để kiểm tra nội dung tệp tin.
  - Tạo tệp `test1.txt` trực tiếp trong CloudShell.
  - Chỉnh sửa và lưu nội dung tệp tin bằng trình soạn thảo `vi`.
  - Sử dụng Actions → Download file để tải tệp từ CloudShell về máy tính cá nhân.
  - Kiểm tra nội dung tệp tin sau khi tải xuống thành công.

- Hiểu được sự thuận tiện của chức năng Upload file và Download file trong CloudShell, hỗ trợ trao đổi dữ liệu giữa môi trường làm việc trên AWS và máy tính cá nhân mà không cần sử dụng thêm công cụ truyền tệp bên ngoài.

- Nắm được quy trình dọn dẹp CloudShell Environment sau khi hoàn thành Workshop, bao gồm:
  - Truy cập mục Actions trong giao diện CloudShell.
  - Lựa chọn chức năng Delete.
  - Xác nhận thao tác xóa bằng cách nhấn Delete.
  - Hoàn tất việc xóa môi trường CloudShell theo hướng dẫn.

- Nhận thức được tầm quan trọng của việc quản lý môi trường làm việc, dữ liệu và tài nguyên AWS sau khi hoàn thành các bài thực hành nhằm tránh lưu trữ những dữ liệu không còn cần thiết và hạn chế các chi phí phát sinh không mong muốn.
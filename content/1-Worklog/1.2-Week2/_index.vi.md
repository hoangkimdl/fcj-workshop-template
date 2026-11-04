
---
title: "Worklog Tuần 2"
date: 2026-10-12
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

- Tìm hiểu AWS Support và vai trò của dịch vụ hỗ trợ kỹ thuật, tài khoản và thanh toán trong quá trình quản lý, vận hành các dịch vụ AWS.
- Tìm hiểu bốn gói hỗ trợ của AWS: Basic, Business Support+, Enterprise Support và Unified Operations, bao gồm các tính năng, kênh hỗ trợ, cấp độ dịch vụ và thời gian phản hồi.
- Nắm được ba loại yêu cầu hỗ trợ chính của AWS: Account and Billing Support, Service Limit Increase và Technical Support.
- Tìm hiểu cách truy cập AWS Support, quản lý gói hỗ trợ, tạo Support Case, lựa chọn mức độ nghiêm trọng phù hợp và theo dõi các yêu cầu đã gửi thông qua AWS Support Center.
- Tìm hiểu dịch vụ AWS Identity and Access Management (IAM) và vai trò của IAM trong việc quản lý danh tính người dùng, quyền truy cập và bảo mật trong tài khoản AWS.
- Tìm hiểu các thành phần chính của IAM, bao gồm IAM User, IAM Group, IAM Policy và IAM Role; hiểu cách tổ chức người dùng và quản lý quyền theo nguyên tắc quyền hạn tối thiểu (Principle of Least Privilege).
- Có kiến thức và kinh nghiệm thực hành trong việc tạo, quản lý IAM Group, IAM User, IAM Role, cấu hình chính sách truy cập và thực hiện chuyển đổi vai trò (Switch Role) thông qua AWS Management Console.
- Phát triển kỹ năng thực hành trong việc xử lý các yêu cầu hỗ trợ AWS và quản lý quyền truy cập IAM, đồng thời tuân thủ các nguyên tắc bảo mật và hạn chế chi phí dịch vụ phát sinh không cần thiết.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu tổng quan về AWS Support và vai trò của dịch vụ trong việc cung cấp hỗ trợ về tài khoản, thanh toán và kỹ thuật cho khách hàng sử dụng AWS.<br>- Tìm hiểu bốn gói hỗ trợ của AWS và các tính năng chính:<br>&nbsp;&nbsp;+ Basic: Cung cấp hỗ trợ cơ bản về tài khoản và thanh toán, AWS Support Forums, AWS Health Dashboard và các tài liệu hướng dẫn.<br>&nbsp;&nbsp;+ Business Support+: Cung cấp khả năng liên hệ Cloud Support Engineers 24/7, số lượng yêu cầu hỗ trợ không giới hạn, các kiểm tra AWS Trusted Advisor, AWS Support API và hỗ trợ phần mềm bên thứ ba.<br>&nbsp;&nbsp;+ Enterprise Support: Bao gồm các tính năng của Business Support+, Technical Account Manager (TAM), Concierge Support Team, Infrastructure Event Management, Well-Architected Reviews và hướng dẫn vận hành.<br>&nbsp;&nbsp;+ Unified Operations: Bao gồm các tính năng của Enterprise Support và AWS Managed Services, giám sát chủ động, quản lý sự cố, quản lý thay đổi, quản lý bản vá, sao lưu và hỗ trợ khôi phục sau thảm họa.<br>- So sánh các gói hỗ trợ về khả năng cung cấp dịch vụ, kênh liên hệ, tính năng bổ sung và thời gian phản hồi.<br>- Tìm hiểu ba loại yêu cầu hỗ trợ chính của AWS:<br>&nbsp;&nbsp;+ Account and Billing Support: Hỗ trợ các vấn đề về tài khoản và thanh toán.<br>&nbsp;&nbsp;+ Service Limit Increase: Yêu cầu tăng giới hạn sử dụng dịch vụ.<br>&nbsp;&nbsp;+ Technical Support: Hỗ trợ xử lý các vấn đề kỹ thuật.<br>- Tìm hiểu những loại yêu cầu hỗ trợ được phép sử dụng trong gói Basic và những yêu cầu cần nâng cấp lên gói hỗ trợ cao hơn.<br>- Làm quen với AWS Support Center và cách truy cập các dịch vụ hỗ trợ thông qua AWS Management Console.<br>- Tìm hiểu quy trình thay đổi gói hỗ trợ thông qua mục Manage Support Plan.<br>- Nhận biết các khoản chi phí hằng tháng có thể phát sinh khi nâng cấp từ gói Basic lên các gói hỗ trợ trả phí. | 12/10/2026 | 12/10/2026 | [AWS Support - Request Support](https://000009.awsfcaj.com/) |
| 3 | - Tìm hiểu quy trình quản lý yêu cầu hỗ trợ AWS và cách sử dụng AWS Support Center để tạo, quản lý và theo dõi các Support Case.<br>- Tìm hiểu cách xác định loại yêu cầu hỗ trợ phù hợp với từng vấn đề:<br>&nbsp;&nbsp;+ Account and Billing Support: Xử lý các vấn đề liên quan đến hóa đơn, thanh toán, xác minh tài khoản, thay đổi thông tin tài khoản và các vấn đề về thuế.<br>&nbsp;&nbsp;+ Service Limit Increase: Cho phép khách hàng yêu cầu tăng giới hạn mặc định của các dịch vụ AWS theo nhu cầu sử dụng tài nguyên.<br>&nbsp;&nbsp;+ Technical Support: Cung cấp hỗ trợ kỹ thuật đối với các dịch vụ AWS và ứng dụng phần mềm bên thứ ba chạy trên AWS, tùy thuộc vào gói hỗ trợ đã đăng ký.<br>- Tìm hiểu các mức độ nghiêm trọng khi gửi yêu cầu hỗ trợ kỹ thuật:<br>&nbsp;&nbsp;+ General Guidance: Hướng dẫn chung, câu hỏi về phát triển hoặc yêu cầu tính năng.<br>&nbsp;&nbsp;+ System Impaired: Một số chức năng không quan trọng của ứng dụng bị ảnh hưởng hoặc hoạt động không bình thường.<br>&nbsp;&nbsp;+ Production System Impaired: Các chức năng quan trọng của hệ thống đang vận hành bị ảnh hưởng hoặc suy giảm hiệu suất.<br>&nbsp;&nbsp;+ Production System Down: Các chức năng quan trọng của hệ thống Production không thể hoạt động.<br>&nbsp;&nbsp;+ Business-Critical System Down: Các chức năng thiết yếu của hệ thống không khả dụng, gây nguy cơ ảnh hưởng nghiêm trọng đến hoạt động kinh doanh.<br>- Tìm hiểu thời gian phản hồi ban đầu tương ứng với từng mức độ nghiêm trọng và gói hỗ trợ áp dụng.<br>- Tìm hiểu cách cung cấp tiêu đề rõ ràng, mô tả chi tiết sự cố, tệp đính kèm liên quan và thông tin tài khoản cần thiết khi tạo Support Case.<br>- Hiểu tầm quan trọng của việc lựa chọn đúng mức độ nghiêm trọng và không tiết lộ thông tin nhạy cảm như mật khẩu hoặc AWS Access Key.<br>- Tìm hiểu cách theo dõi các yêu cầu đã gửi thông qua mục Support Cases và phản hồi những câu hỏi bổ sung từ đội ngũ AWS Support. | 13/10/2026 | 13/10/2026 | [AWS Support - Request Support](https://000009.awsfcaj.com/) |
| 4 | - **Thực hành:** Tìm hiểu quy trình tạo và gửi yêu cầu hỗ trợ AWS thông qua AWS Support Center.<br>&nbsp;&nbsp;+ Truy cập AWS Support Center thông qua AWS Management Console.<br>&nbsp;&nbsp;+ Chọn Create case để bắt đầu tạo yêu cầu hỗ trợ mới.<br>&nbsp;&nbsp;+ Chọn Account and Billing Support đối với tình huống cần hỗ trợ liên quan đến hóa đơn.<br>&nbsp;&nbsp;+ Chọn Account and billing làm danh mục hỗ trợ.<br>&nbsp;&nbsp;+ Chọn Invoice làm dịch vụ và Question About My Invoice làm loại vấn đề cần hỗ trợ.<br>&nbsp;&nbsp;+ Chọn General question làm mức độ nghiêm trọng đối với tình huống hỏi thông tin hóa đơn.<br>&nbsp;&nbsp;+ Nhập tiêu đề rõ ràng và mô tả chi tiết nội dung cần hỗ trợ.<br>&nbsp;&nbsp;+ Truy cập Billing and Cost Management → Bills → Invoices để tìm và tải hóa đơn cần thiết.<br>&nbsp;&nbsp;+ Đính kèm hóa đơn liên quan và cung cấp Invoice ID tương ứng.<br>&nbsp;&nbsp;+ Chọn Web trong mục Contact us và kiểm tra lại thông tin trước khi gửi yêu cầu.<br>&nbsp;&nbsp;+ Gửi yêu cầu hỗ trợ và tìm hiểu cách truy cập Support Cases để xem chi tiết, trạng thái xử lý.<br>- **Thực hành:** Tìm hiểu quy trình lựa chọn mức độ nghiêm trọng và so sánh thời gian phản hồi dự kiến giữa các gói hỗ trợ.<br>&nbsp;&nbsp;+ Xác định mức độ nghiêm trọng phù hợp dựa trên mức độ ảnh hưởng của sự cố.<br>&nbsp;&nbsp;+ Phân biệt các trường hợp hướng dẫn chung, hệ thống bị ảnh hưởng, hệ thống Production bị gián đoạn và hệ thống thiết yếu của doanh nghiệp ngừng hoạt động.<br>&nbsp;&nbsp;+ Kiểm tra các kênh hỗ trợ và cam kết thời gian phản hồi của từng gói hỗ trợ.<br>- Tìm hiểu quy trình thay đổi gói hỗ trợ và nhận biết các khoản chi phí hằng tháng có thể phát sinh khi sử dụng các gói hỗ trợ trả phí.<br>- Nắm được cách cung cấp đầy đủ thông tin cho yêu cầu hỗ trợ, theo dõi cập nhật và phản hồi các yêu cầu bổ sung từ AWS Support.<br>- Kiểm tra các biện pháp bảo mật khi gửi yêu cầu hỗ trợ, bảo đảm không tiết lộ mật khẩu, Access Key và những thông tin xác thực nhạy cảm khác. | 14/10/2026 | 14/10/2026 | [AWS Support - Request Support](https://000009.awsfcaj.com/) |
| 5 | - Tìm hiểu kiến thức cơ bản về AWS Identity and Access Management (IAM) và vai trò của IAM trong việc quản lý danh tính, xác thực và quyền truy cập vào các tài nguyên AWS.<br>- Tìm hiểu các thành phần chính của IAM:<br>&nbsp;&nbsp;+ IAM User: Đại diện cho một người dùng hoặc danh tính dịch vụ trong tài khoản AWS.<br>&nbsp;&nbsp;+ IAM Group: Nhóm nhiều IAM User nhằm quản lý quyền truy cập một cách tập trung.<br>&nbsp;&nbsp;+ IAM Policy: Tài liệu định dạng JSON xác định những hành động và tài nguyên mà người dùng hoặc vai trò được phép hoặc bị từ chối truy cập.<br>&nbsp;&nbsp;+ IAM Role: Cung cấp quyền truy cập tạm thời cho các thực thể được tin cậy thông qua cơ chế AssumeRole.<br>- Tìm hiểu sự khác biệt giữa IAM User, IAM Group, IAM Policy và IAM Role.<br>- Tìm hiểu cách gắn IAM Policy cho User, Group và Role để kiểm soát quyền truy cập.<br>- Tìm hiểu AWS Managed Policies và Customer Managed Policies.<br>- Nắm được nguyên tắc Principle of Least Privilege và mô hình phân quyền dựa trên vai trò (Role-Based Access Control - RBAC).<br>- Tìm hiểu Trust Policy, Permission Policy, thông tin xác thực bảo mật tạm thời và vai trò của IAM Role trong quản lý quyền truy cập an toàn.<br>- Tìm hiểu các biện pháp bảo mật tốt nhất, bao gồm hạn chế sử dụng tài khoản Root, tạo IAM User riêng cho từng người dùng và thường xuyên kiểm tra, đánh giá các quyền đã cấp. | 15/10/2026 | 15/10/2026 | [AWS IAM - Access Control](https://000002.awsfcaj.com/) |
| 6 | - **Thực hành:** Tạo và cấu hình IAM Group, IAM User thông qua AWS Management Console.<br>&nbsp;&nbsp;+ Truy cập dịch vụ IAM từ AWS Management Console.<br>&nbsp;&nbsp;+ Tạo nhóm AdminGroup để quản lý tập trung những người dùng có quyền quản trị.<br>&nbsp;&nbsp;+ Gắn chính sách AdministratorAccess cho AdminGroup theo hướng dẫn của workshop.<br>&nbsp;&nbsp;+ Tạo IAM User với tên AdminUser và cấu hình quyền truy cập AWS Management Console.<br>&nbsp;&nbsp;+ Thêm AdminUser vào AdminGroup để người dùng kế thừa quyền của nhóm.<br>&nbsp;&nbsp;+ Truy cập đường dẫn đăng nhập dành cho IAM User và đăng nhập bằng thông tin tài khoản AdminUser.<br>- **Thực hành:** Tạo và cấu hình IAM Role và OperatorUser.<br>&nbsp;&nbsp;+ Tạo Admin Role với thực thể được tin cậy và quyền quản trị phù hợp.<br>&nbsp;&nbsp;+ Tạo IAM User với tên OperatorUser và cấu hình quyền cho phép thực hiện thao tác AssumeRole.<br>&nbsp;&nbsp;+ Cấu hình Trust Policy để xác định những danh tính được phép đảm nhận vai trò.<br>&nbsp;&nbsp;+ Cấu hình Permission Policy để cho phép OperatorUser thực hiện thao tác AssumeRole.<br>&nbsp;&nbsp;+ Đăng nhập AWS Management Console bằng thông tin tài khoản OperatorUser.<br>&nbsp;&nbsp;+ Thực hiện Switch Role để đảm nhận Admin Role đã tạo trước đó.<br>&nbsp;&nbsp;+ Kiểm tra vai trò sau khi chuyển đổi và xác minh các quyền có thể sử dụng trong phiên làm việc.<br>- Tìm hiểu thông tin xác thực bảo mật tạm thời, thời lượng phiên làm việc của Role và cách theo dõi hoạt động thông qua AWS CloudTrail.<br>- Tìm hiểu quy trình dọn dẹp IAM, bao gồm xóa các IAM User và IAM Group được tạo trong bài thực hành, đồng thời kiểm tra để bảo đảm các tài nguyên tạm thời đã được xử lý. | 16/10/2026 | 16/10/2026 | [AWS IAM - Access Control](https://000002.awsfcaj.com/) |

### Kết quả đạt được trong tuần 2:

- Nắm được tổng quan về AWS Support và vai trò của dịch vụ trong việc cung cấp hỗ trợ về tài khoản, thanh toán và kỹ thuật cho khách hàng sử dụng AWS.

- Hiểu được bốn gói hỗ trợ chính của AWS và các tính năng tương ứng:
  - **Basic:** Cung cấp hỗ trợ cơ bản về tài khoản và thanh toán, AWS Support Forums, AWS Health Dashboard và quyền truy cập vào tài liệu hướng dẫn, tài nguyên thực hành tốt nhất của AWS.
  - **Business Support+:** Cung cấp khả năng liên hệ Cloud Support Engineers 24/7 thông qua điện thoại, trò chuyện và email; không giới hạn số lượng Support Case; hỗ trợ đầy đủ các kiểm tra AWS Trusted Advisor; AWS Support API và hỗ trợ phần mềm bên thứ ba.
  - **Enterprise Support:** Bao gồm các tính năng của Business Support+, Technical Account Manager (TAM), Concierge Support Team, Infrastructure Event Management, Well-Architected Reviews, hướng dẫn vận hành và tài nguyên đào tạo.
  - **Unified Operations:** Cung cấp các tính năng của Enterprise Support kết hợp AWS Managed Services, giám sát chủ động, quản lý sự cố, quản lý thay đổi, quản lý bản vá, sao lưu, khôi phục sau thảm họa và các hoạt động bảo mật.

- Hiểu được sự khác biệt giữa các gói hỗ trợ về dịch vụ được cung cấp, kênh liên hệ, hỗ trợ vận hành và cam kết thời gian phản hồi ban đầu.

- Nắm được ba loại yêu cầu hỗ trợ chính của AWS:
  - **Account and Billing Support:** Hỗ trợ các vấn đề liên quan đến tài khoản, hóa đơn, thanh toán, xác minh tài khoản, thay đổi thông tin tài khoản và các vấn đề về thuế.
  - **Service Limit Increase:** Cho phép khách hàng yêu cầu tăng giới hạn sử dụng mặc định của các dịch vụ AWS theo nhu cầu về tài nguyên.
  - **Technical Support:** Cung cấp hỗ trợ xử lý các vấn đề kỹ thuật liên quan đến dịch vụ AWS và ứng dụng phần mềm bên thứ ba chạy trên AWS, tùy thuộc vào gói hỗ trợ đã đăng ký.

- Hiểu được khả năng sử dụng các loại yêu cầu hỗ trợ theo từng gói hỗ trợ, đặc biệt là Account and Billing Support và Service Limit Increase có thể được sử dụng với gói Basic, trong khi Technical Support yêu cầu từ gói Business Support+ trở lên theo hướng dẫn của workshop.

- Làm quen với AWS Support Center và hiểu vai trò của công cụ trong việc tập trung tạo, quản lý và theo dõi các yêu cầu hỗ trợ.

- Biết cách truy cập AWS Support thông qua AWS Management Console và nắm được quy trình thay đổi gói hỗ trợ thông qua mục Manage Support Plan.

- Nhận thức được rằng việc nâng cấp từ gói Basic lên các gói hỗ trợ trả phí có thể làm tăng chi phí hằng tháng của tài khoản AWS, do đó cần lựa chọn gói hỗ trợ dựa trên nhu cầu vận hành thực tế.

- Nắm được năm mức độ nghiêm trọng được sử dụng khi gửi yêu cầu hỗ trợ kỹ thuật và thời gian phản hồi ban đầu tương ứng:
  - **General Guidance:** 24 giờ đối với các câu hỏi hướng dẫn chung về phát triển hoặc yêu cầu tính năng.
  - **System Impaired:** 12 giờ khi các chức năng không quan trọng của ứng dụng bị ảnh hưởng.
  - **Production System Impaired:** 4 giờ khi các chức năng quan trọng của hệ thống Production bị ảnh hưởng hoặc suy giảm.
  - **Production System Down:** 1 giờ khi các chức năng quan trọng của hệ thống Production không khả dụng.
  - **Business-Critical System Down:** 15 phút khi các chức năng thiết yếu của hệ thống không khả dụng và hoạt động kinh doanh có nguy cơ bị ảnh hưởng nghiêm trọng.

- Hiểu rằng các mức độ nghiêm trọng và thời gian phản hồi cam kết phụ thuộc vào gói hỗ trợ đã đăng ký; mức Business-Critical System Down được cung cấp theo workshop đối với Enterprise Support và Unified Operations.

- Có kiến thức thực hành về quy trình tạo yêu cầu hỗ trợ AWS thông qua AWS Support Center, bao gồm:
  - Truy cập giao diện Support Center.
  - Lựa chọn Create case để tạo yêu cầu hỗ trợ mới.
  - Chọn loại yêu cầu hỗ trợ phù hợp.
  - Lựa chọn dịch vụ, danh mục vấn đề và mức độ nghiêm trọng.
  - Nhập tiêu đề rõ ràng và mô tả chi tiết vấn đề cần hỗ trợ.
  - Đính kèm các tài liệu liên quan.
  - Cung cấp Invoice ID đối với những yêu cầu liên quan đến hóa đơn.
  - Lựa chọn phương thức liên hệ phù hợp.
  - Kiểm tra thông tin và gửi yêu cầu hỗ trợ.
  - Truy cập Support Cases để theo dõi trạng thái và xem chi tiết yêu cầu đã gửi.

- Hiểu được quy trình gửi yêu cầu hỗ trợ liên quan đến hóa đơn, bao gồm cách tìm và tải hóa đơn tại Billing and Cost Management → Bills → Invoices và cung cấp thông tin hóa đơn cần thiết khi yêu cầu AWS hỗ trợ.

- Nhận thức được tầm quan trọng của việc cung cấp thông tin đầy đủ, chính xác khi tạo Support Case nhằm giúp đội ngũ AWS Support hiểu rõ vấn đề và đưa ra phương án hỗ trợ phù hợp.

- Hiểu được cách theo dõi các cập nhật của Support Case, phản hồi khi được yêu cầu bổ sung thông tin và duy trì trao đổi với đội ngũ AWS Support cho đến khi vấn đề được xử lý.

- Nhận thức được tầm quan trọng của việc bảo vệ thông tin tài khoản khi trao đổi với AWS Support, đặc biệt là không tiết lộ mật khẩu, Access Key và các thông tin xác thực nhạy cảm khác.

- Nắm được tổng quan về AWS Identity and Access Management (IAM), hiểu vai trò của IAM trong việc quản lý danh tính, xác thực, cấp quyền và kiểm soát truy cập đối với các tài nguyên AWS.

- Hiểu được chức năng và đặc điểm của các thành phần IAM chính, bao gồm:
  - **IAM User:** Đại diện cho một người dùng hoặc danh tính dịch vụ trong tài khoản AWS, có thông tin xác thực và quyền truy cập tương ứng.
  - **IAM Group:** Tập hợp nhiều IAM User thành các nhóm nhằm đơn giản hóa việc quản lý quyền và kiểm soát truy cập tập trung.
  - **IAM Policy:** Tài liệu định dạng JSON xác định những hành động được phép hoặc bị từ chối trên các tài nguyên AWS cụ thể.
  - **IAM Role:** Cung cấp thông tin xác thực bảo mật và quyền truy cập tạm thời cho các thực thể được tin cậy thông qua cơ chế đảm nhận vai trò (AssumeRole).

- Hiểu được cách IAM Group hỗ trợ đơn giản hóa việc quản lý quyền truy cập bằng cách cho phép quản trị viên gán chính sách cho nhóm thay vì phải quản lý riêng quyền của từng người dùng.

- Nắm được cách IAM Policy kiểm soát quyền truy cập vào các dịch vụ và tài nguyên AWS thông qua:
  - Xác định các hành động được phép và bị từ chối.
  - Chỉ định quyền truy cập ở cấp độ tài nguyên.
  - Sử dụng AWS Managed Policies và Customer Managed Policies.
  - Áp dụng điều kiện truy cập dựa trên thẻ (Tag), thời gian hoặc vị trí.
  - Tuân thủ nguyên tắc Principle of Least Privilege.

- Phân biệt được AWS Managed Policies và Customer Managed Policies, đồng thời hiểu tầm quan trọng của việc kiểm tra, thử nghiệm chính sách thông qua AWS Policy Simulator trước khi áp dụng.

- Nắm được vai trò của IAM Role trong việc cung cấp quyền truy cập tạm thời và an toàn, bao gồm:
  - Trust Policy xác định những thực thể được phép đảm nhận vai trò.
  - Permission Policy xác định những hành động mà vai trò được phép thực hiện.
  - Thông tin xác thực bảo mật tạm thời có cơ chế tự động hết hạn.
  - Truy cập giữa nhiều tài khoản AWS và giao tiếp giữa các dịch vụ.
  - Thời lượng phiên làm việc của Role và khả năng theo dõi hoạt động thông qua CloudTrail.

- Có kiến thức và kinh nghiệm thực hành trong việc tạo và quản lý IAM Group, IAM User, bao gồm:
  - Tạo AdminGroup để quản lý tập trung các quyền quản trị.
  - Gắn chính sách AdministratorAccess cho nhóm quản trị trong môi trường thực hành.
  - Tạo IAM User với tên AdminUser.
  - Thêm AdminUser vào AdminGroup để kế thừa quyền của nhóm.
  - Cấu hình quyền truy cập AWS Management Console.
  - Sử dụng đường dẫn đăng nhập dành cho IAM User để truy cập AWS bằng tài khoản AdminUser.

- Có kiến thức thực hành về tạo IAM Role và cấu hình phân quyền dựa trên vai trò, bao gồm:
  - Tạo Admin Role với mối quan hệ tin cậy và quyền truy cập phù hợp.
  - Tạo OperatorUser để thực hiện truy cập theo vai trò.
  - Cấu hình Trust Policy và Permission Policy.
  - Cấp quyền cho OperatorUser thực hiện thao tác AssumeRole.
  - Đăng nhập bằng tài khoản OperatorUser và thực hiện Switch Role.
  - Kiểm tra quyền truy cập sau khi đảm nhận vai trò mới.

- Hiểu được lợi ích của việc sử dụng IAM Role và thông tin xác thực tạm thời thay vì chia sẻ thông tin xác thực dài hạn, đặc biệt về bảo mật, kiểm soát truy cập và khả năng kiểm toán.

- Tìm hiểu cách dọn dẹp các tài nguyên IAM được tạo trong quá trình thực hành, bao gồm xóa IAM User, IAM Group tạm thời và kiểm tra lại quá trình dọn dẹp nhằm duy trì bảo mật tài khoản.

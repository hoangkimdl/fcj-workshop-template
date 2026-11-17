---
title: "Worklog Tuần 6"
date: 2026-11-09
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

- Tìm hiểu tổng quan về Amazon Simple Storage Service (Amazon S3), vai trò của dịch vụ lưu trữ đối tượng trong AWS Cloud và các khái niệm quan trọng như Bucket, Object, Storage Classes và Access Control.
- Nắm được cách tạo và cấu hình Amazon S3 Bucket, quản lý các đối tượng lưu trữ và thực hành tải dữ liệu từ máy tính cá nhân lên S3.
- Thực hành triển khai Static Website Hosting trực tiếp trên Amazon S3, cấu hình quyền truy cập công khai cho các tệp tin website và kiểm tra khả năng truy cập thông qua Website Endpoint.
- Tìm hiểu Amazon CloudFront và thực hành tích hợp CloudFront với S3 để phân phối nội dung website, cải thiện tốc độ truy cập và tăng cường bảo mật cho dữ liệu lưu trữ.
- Tìm hiểu và thực hành Amazon S3 Bucket Versioning nhằm lưu giữ nhiều phiên bản của đối tượng, hỗ trợ theo dõi thay đổi và khôi phục dữ liệu khi cần thiết.
- Thực hành di chuyển các đối tượng giữa các S3 Bucket bằng chức năng Move Objects và tìm hiểu Amazon S3 Cross-Region Replication (CRR) để tự động sao chép dữ liệu giữa các AWS Region.
- Tìm hiểu các nguyên tắc bảo mật, tối ưu hiệu năng và quản lý chi phí khi sử dụng Amazon S3, bao gồm Block Public Access, Bucket Policies, Encryption, Lifecycle Policies và CloudFront Origin Access Control (OAC).
- Nắm được quy trình kiểm tra, dọn dẹp và xóa các tài nguyên Amazon S3, CloudFront sau khi hoàn thành Workshop nhằm hạn chế chi phí phát sinh không cần thiết.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| Thứ 2 | **Tìm hiểu Amazon S3 và thực hành tạo Bucket, tải dữ liệu lên S3**<br><br> - Tìm hiểu tổng quan về Amazon Simple Storage Service (Amazon S3), một dịch vụ lưu trữ đối tượng có khả năng mở rộng, cung cấp tính sẵn sàng, độ bền, bảo mật và hiệu năng cao trên AWS Cloud.<br> - Tìm hiểu vai trò của Amazon S3 trong các trường hợp sử dụng phổ biến như lưu trữ dữ liệu, triển khai website tĩnh, sao lưu và khôi phục dữ liệu, lưu trữ ứng dụng, phân tích dữ liệu và Disaster Recovery.<br> - Phân biệt hai thành phần cơ bản của Amazon S3:<br>&nbsp;&nbsp;+ **S3 Bucket:** Vùng chứa cấp cao nhất được sử dụng để lưu trữ và tổ chức các đối tượng dữ liệu. Mỗi Bucket có tên duy nhất trên toàn cầu và được tạo trong một AWS Region cụ thể.<br>&nbsp;&nbsp;+ **S3 Object:** Đối tượng dữ liệu thực tế được lưu trữ bên trong Bucket, bao gồm nội dung dữ liệu và Metadata liên quan.<br> - Tìm hiểu các đặc điểm của Object như Object Key, Metadata, dung lượng lưu trữ và quyền truy cập ở cấp độ đối tượng.<br> - Tìm hiểu các Storage Classes của Amazon S3, bao gồm S3 Standard, S3 Intelligent-Tiering, S3 Standard-IA, S3 Glacier và S3 Glacier Deep Archive; phân biệt mục đích sử dụng của từng lớp lưu trữ theo tần suất truy cập và nhu cầu lưu trữ dữ liệu.<br> - Tìm hiểu các tính năng quan trọng của Amazon S3 như Encryption, Access Control, Versioning, Lifecycle Management, Cross-Region Replication và S3 Storage Lens.<br> - Truy cập AWS Management Console và mở dịch vụ Amazon S3 thông qua thanh tìm kiếm dịch vụ.<br> - Thực hành tạo S3 Bucket mới bằng chức năng Create bucket, lựa chọn AWS Region `ap-southeast-1` (Singapore) theo hướng dẫn Workshop.<br> - Đặt tên Bucket theo mẫu `aws-first-cloud-ai-journey-1902`; trường hợp tên đã được sử dụng thì bổ sung hoặc thay đổi số để đảm bảo tính duy nhất trên toàn cầu.<br> - Cấu hình Object Ownership với tùy chọn ACLs disabled (recommended), giữ nguyên các thiết lập Block all public access, tắt Bucket Versioning trong bước khởi tạo và kiểm tra tùy chọn mã hóa mặc định SSE-S3.<br> - Giữ các thiết lập nâng cao theo mặc định, kiểm tra lại các thông số cấu hình và hoàn tất việc tạo S3 Bucket.<br> - Kiểm tra thông tin Bucket sau khi tạo, bao gồm tên Bucket, AWS Region, trạng thái quyền truy cập và dung lượng lưu trữ ban đầu.<br> - Thực hành tải mã nguồn website mẫu từ GitHub về máy tính cá nhân, giải nén thư mục `S3-Website-main` để chuẩn bị dữ liệu triển khai website.<br> - Truy cập S3 Bucket vừa tạo, lựa chọn Upload và sử dụng chức năng tải lên toàn bộ thư mục, tệp tin website đã giải nén.<br> - Kiểm tra danh sách Objects trong Bucket sau khi tải lên nhằm xác nhận các tệp HTML, CSS, JavaScript, hình ảnh và các tài nguyên liên quan đã được lưu trữ thành công.<br> - Tìm hiểu cách tổ chức dữ liệu trong S3 thông qua Object Keys và các Prefix để thuận tiện cho việc quản lý các tệp tin. | 09/11/2026 | 09/11/2026 | [Start With Amazon S3](https://000057.awsfcaj.com/)<br>[Introduction](https://000057.awsfcaj.com/1-introduce/)<br>[Create S3 Bucket](https://000057.awsfcaj.com/2-prerequiste/2.1-creates3bucket/)<br>[Download Data](https://000057.awsfcaj.com/2-prerequiste/2.2-uploaddata/) |
| Thứ 3 | **Thực hành triển khai Static Website Hosting trên Amazon S3 và cấu hình quyền truy cập công khai**<br><br> - Tìm hiểu Static Website Hosting trên Amazon S3, cho phép lưu trữ và phân phối trực tiếp các nội dung tĩnh như HTML, CSS, JavaScript và hình ảnh mà không cần triển khai máy chủ web riêng.<br> - Tìm hiểu những lợi ích của Static Website Hosting như tiết kiệm chi phí, khả năng mở rộng tự động, tính tin cậy cao và không cần quản lý máy chủ web.<br> - Thực hành truy cập S3 Bucket, mở thẻ Properties và tìm đến mục Static website hosting.<br> - Bật tính năng Static Website Hosting bằng tùy chọn Enable, lựa chọn loại hình Host a static website và cấu hình tệp mặc định `index.html` cùng tệp lỗi tùy chọn `error.html`.<br> - Lưu cấu hình và kiểm tra Website Endpoint được Amazon S3 tạo sau khi bật tính năng lưu trữ website tĩnh.<br> - Tìm hiểu sự khác nhau giữa Website Endpoint và S3 Bucket Endpoint, đồng thời nhận biết Website Endpoint sử dụng HTTP và cần CloudFront nếu muốn phân phối website qua HTTPS.<br> - Tìm hiểu cơ chế Block Public Access của Amazon S3 và vai trò của tính năng này trong việc ngăn chặn truy cập công khai ngoài ý muốn đến Bucket và Objects.<br> - Thực hành truy cập thẻ Permissions, mở mục Block public access và bỏ chọn Block all public access theo yêu cầu của bài thực hành Static Website Hosting.<br> - Xác nhận thay đổi bằng cách nhập từ khóa `confirm` trong hộp thoại xác nhận và lưu cấu hình quyền truy cập công khai.<br> - Tìm hiểu các cấp độ quản lý quyền truy cập của S3, bao gồm Bucket-level permissions và Object-level permissions; phân biệt vai trò của ACLs, Bucket Policies và IAM Policies.<br> - Thực hành thay đổi Object Ownership từ Bucket owner enforced sang Bucket owner preferred và bật ACLs để hỗ trợ cấu hình quyền truy cập ở cấp độ đối tượng.<br> - Tại mục Object Ownership, lựa chọn ACLs enabled, xác nhận I acknowledge that ACLs will be restored và lưu cấu hình theo hướng dẫn Workshop.<br> - Truy cập tab Objects, lựa chọn các tệp tin website cần công khai như HTML, CSS, JavaScript và hình ảnh; thực hiện Actions → Make public using ACL để cấp quyền đọc công khai cho các đối tượng được lựa chọn.<br> - Kiểm tra trạng thái quyền truy cập của các Objects sau khi cấu hình và xác nhận các tệp tin website có thể được tải xuống bởi người dùng Internet.<br> - Truy cập Properties → Static website hosting, sao chép Bucket website endpoint và mở đường dẫn trên trình duyệt để kiểm tra giao diện website mẫu.<br> - Sử dụng Developer Tools của trình duyệt, mở thẻ Network và tải lại trang để quan sát thời gian tải website thông qua S3 Website Endpoint trước khi tích hợp CloudFront.<br> - Nhận biết rủi ro bảo mật khi cho phép các đối tượng truy cập công khai và hiểu rằng chỉ những nội dung thực sự cần công khai mới được cấp quyền truy cập phù hợp. | 10/11/2026 | 10/11/2026 | [Start With Amazon S3](https://000057.awsfcaj.com/)<br>[Enable Static Website Feature](https://000057.awsfcaj.com/3-staticwebsite/)<br>[Configuring Public Access Block](https://000057.awsfcaj.com/4-blockpublicaccess/)<br>[Configuring Public Objects](https://000057.awsfcaj.com/5-publicobject/)<br>[Test Website](https://000057.awsfcaj.com/6-testwebsite/) |
| Thứ 4 | **Tìm hiểu và thực hành tích hợp Amazon CloudFront với S3 để phân phối website**<br><br> - Tìm hiểu Amazon CloudFront và vai trò của dịch vụ Content Delivery Network (CDN) trong việc phân phối nội dung thông qua hệ thống Edge Locations trên toàn cầu.<br> - Tìm hiểu nguyên lý hoạt động của CloudFront, trong đó nội dung được phân phối từ các vị trí biên gần người dùng nhằm giảm độ trễ, cải thiện tốc độ tải trang và nâng cao trải nghiệm truy cập website.<br> - Tìm hiểu lợi ích của việc kết hợp Amazon CloudFront với S3, đặc biệt là khả năng phân phối nội dung website mà không cần công khai trực tiếp S3 Bucket.<br> - Thực hành quay lại S3 Bucket, truy cập Permissions và bật lại Block all public access nhằm ngăn chặn người dùng Internet truy cập công khai trực tiếp vào Bucket và Objects.<br> - Xác nhận thay đổi bằng cách nhập `confirm`, lưu cấu hình và kiểm tra trạng thái Block Public Access đã được bật.<br> - Thực hành mở cửa sổ trình duyệt ẩn danh bằng tổ hợp phím `Ctrl + Shift + N`, truy cập lại S3 Website Endpoint để kiểm tra khả năng truy cập sau khi bật Block Public Access.<br> - Tìm hiểu sự khác nhau giữa việc truy cập website trực tiếp thông qua S3 Endpoint và truy cập thông qua CloudFront Distribution Domain Name.<br> - Truy cập Amazon CloudFront và lựa chọn Create distribution để tạo Distribution mới.<br> - Lựa chọn gói miễn phí được Workshop hướng dẫn sử dụng cho mục đích học tập, sau đó đặt Distribution Name phù hợp.<br> - Tại phần Origin, lựa chọn Amazon S3 làm Origin Type và sử dụng Browse S3 để chọn Bucket đã tạo ở các bước trước làm nguồn cung cấp nội dung.<br> - Giữ các thiết lập mặc định theo hướng dẫn Workshop, kiểm tra thông tin cấu hình và lựa chọn Create distribution để hoàn tất quá trình khởi tạo.<br> - Theo dõi trạng thái triển khai Distribution trên giao diện CloudFront và tìm hiểu trạng thái Deploying trong quá trình AWS phân phối cấu hình đến các Edge Locations.<br> - Thực hành chỉnh sửa Distribution, cấu hình Default root object là `index.html` để CloudFront có thể tự động hiển thị trang chủ khi người dùng truy cập Domain Name của Distribution.<br> - Truy cập mục Origins, lựa chọn Origin vừa tạo và mở phần chỉnh sửa cấu hình để sao chép Bucket Policy được CloudFront cung cấp.<br> - Quay lại S3 Bucket, truy cập Permissions → Bucket policy, dán Bucket Policy đã sao chép và lưu cấu hình nhằm cấp quyền truy cập phù hợp cho CloudFront.<br> - Chờ CloudFront hoàn tất quá trình triển khai, kiểm tra trạng thái Distribution và sao chép Distribution Domain Name.<br> - Thực hành mở Distribution Domain Name trên trình duyệt để kiểm tra giao diện website được phân phối thông qua CloudFront mà không cần công khai S3 Bucket.<br> - Sử dụng Developer Tools → Network để kiểm tra thời gian tải website thông qua CloudFront và so sánh với kết quả truy cập trực tiếp từ S3 Website Endpoint.<br> - Tìm hiểu cách kiểm tra Response Headers và thuộc tính `x-amz-cf-pop` nhằm xác định Point of Presence (PoP) đang cung cấp nội dung website; nhận biết ví dụ `SGN50-P2` tương ứng với Ho Chi Minh City trong hướng dẫn Workshop.<br> - So sánh kết quả tải trang trước và sau khi tích hợp CloudFront, hiểu được vai trò của Edge Locations và cơ chế phân phối nội dung trong việc giảm độ trễ.<br> - Tìm hiểu thêm Origin Access Control (OAC) và nguyên tắc sử dụng Bucket Policy để cấp quyền truy cập cho CloudFront thay vì công khai toàn bộ dữ liệu trong môi trường triển khai thực tế. | 11/11/2026 | 11/11/2026 | [Start With Amazon S3](https://000057.awsfcaj.com/)<br>[Accelerate Static Websites with CloudFront](https://000057.awsfcaj.com/7-cloudfront/)<br>[Block All Public Access](https://000057.awsfcaj.com/7-cloudfront/7.1-block_all_public_access/)<br>[Configure Amazon CloudFront](https://000057.awsfcaj.com/7-cloudfront/7.2-configure_amazon_cloudfront/)<br>[Test Amazon CloudFront](https://000057.awsfcaj.com/7-cloudfront/7.3-test_cloudfront/) |
| Thứ 5 | **Tìm hiểu và thực hành Amazon S3 Bucket Versioning, di chuyển Objects giữa các Bucket**<br><br> - Tìm hiểu Amazon S3 Bucket Versioning, một tính năng cho phép lưu giữ nhiều phiên bản của cùng một đối tượng trong một Bucket nhằm hạn chế mất dữ liệu khi xảy ra thao tác ghi đè hoặc xóa nhầm.<br> - Tìm hiểu các lợi ích của Versioning như bảo vệ dữ liệu, theo dõi lịch sử thay đổi, khôi phục phiên bản trước đó, đáp ứng yêu cầu lưu trữ dữ liệu và hỗ trợ cộng tác.<br> - Tìm hiểu cơ chế hoạt động của Versioning, trong đó mỗi phiên bản Object được gắn một Version ID riêng; thao tác tải lên phiên bản mới không ghi đè vĩnh viễn phiên bản trước đó.<br> - Phân biệt ba trạng thái của Bucket Versioning gồm Unversioned, Versioning-enabled và Versioning-suspended; hiểu được khả năng tạo phiên bản mới và duy trì các phiên bản cũ trong từng trạng thái.<br> - Thực hành truy cập S3 Bucket, mở Properties → Bucket Versioning và lựa chọn Edit để bật tính năng Enable Versioning.<br> - Mở tệp `index.html` trong thư mục mã nguồn đã tải về máy tính, sử dụng Notepad để chỉnh sửa nội dung trong thẻ body theo hướng dẫn Workshop, thay đổi nội dung `AWS First Cloud AI Journey` thành `HỌC CLOUD AI VUI BIẾT BAO <3`.<br> - Lưu thay đổi bằng tổ hợp phím `Ctrl + S` và tải lại tệp `index.html` đã chỉnh sửa lên S3 Bucket bằng chức năng Upload.<br> - Tìm kiếm `index.html`, bật tùy chọn Show versions để kiểm tra các phiên bản của cùng một Object và xác nhận hệ thống đã lưu giữ hai phiên bản với thời gian chỉnh sửa khác nhau.<br> - Tìm hiểu ảnh hưởng của Versioning đến dung lượng lưu trữ và chi phí AWS, nhận thức được việc mỗi phiên bản được lưu trữ như một bản sao đầy đủ và có thể phát sinh thêm chi phí.<br> - Tìm hiểu vai trò của Lifecycle Policies trong việc tự động quản lý các phiên bản cũ và khả năng sử dụng MFA Delete để tăng cường bảo vệ dữ liệu.<br> - Tìm hiểu chức năng Move Objects trên Amazon S3, cho phép di chuyển đối tượng đến một thư mục (Prefix) khác trong cùng Bucket hoặc chuyển sang một Bucket khác.<br> - Thực hành tạo một S3 Bucket mới theo mẫu `aws-first-cloud-ai-journey-xxxx-move`, giữ các thiết lập mặc định theo hướng dẫn Workshop và hoàn tất quá trình tạo Bucket đích.<br> - Truy cập Bucket nguồn, lựa chọn tất cả Objects và sử dụng Actions → Calculate total size để kiểm tra tổng số lượng cũng như dung lượng dữ liệu trước khi di chuyển.<br> - Thực hành sử dụng Actions → Move, lựa chọn General purpose bucket làm loại đích, mở Browse S3 và lựa chọn Bucket nhận dữ liệu vừa tạo.<br> - Giữ nguyên các thiết lập Copy source settings trong phần Additional copy settings, sau đó thực hiện Move để bắt đầu quá trình di chuyển dữ liệu.<br> - Theo dõi quá trình di chuyển, đóng thông báo sau khi hoàn tất và truy cập Bucket đích để kiểm tra danh sách Objects.<br> - Sử dụng Calculate total size tại Bucket đích để đối chiếu số lượng và tổng dung lượng dữ liệu sau khi di chuyển, xác nhận các đối tượng đã được chuyển thành công.<br> - Hiểu được lợi ích của việc di chuyển Objects trong quá trình tổ chức, phân loại và quản lý dữ liệu giữa các S3 Bucket. | 12/11/2026 | 12/11/2026 | [Start With Amazon S3](https://000057.awsfcaj.com/)<br>[Bucket Versioning](https://000057.awsfcaj.com/8-versioning/)<br>[Move Objects](https://000057.awsfcaj.com/9-moveobject/) |
| Thứ 6 | **Thực hành Amazon S3 Cross-Region Replication và tổng kết, dọn dẹp tài nguyên sau Workshop**<br><br> - Tìm hiểu Amazon S3 Cross-Region Replication (CRR), tính năng tự động sao chép các Objects giữa những S3 Bucket thuộc các AWS Region khác nhau.<br> - Tìm hiểu các lợi ích của CRR trong việc tăng cường khả năng dự phòng dữ liệu, hỗ trợ Disaster Recovery, đáp ứng yêu cầu tuân thủ, phân phối dữ liệu theo khu vực địa lý và duy trì tính liên tục của hệ thống.<br> - Tìm hiểu nguyên lý sao chép dữ liệu bất đồng bộ (Asynchronous Replication), trong đó các Objects được tự động sao chép đến Bucket đích; quá trình sao chép thường hoàn tất trong khoảng thời gian được AWS hướng dẫn là tối đa khoảng 15 phút tùy điều kiện thực tế.<br> - Tìm hiểu những điều kiện cần thiết để cấu hình CRR, bao gồm bật Bucket Versioning trên cả Source Bucket và Destination Bucket, thiết lập Replication Rule và sử dụng IAM Role để cấp quyền sao chép dữ liệu.<br> - Tìm hiểu các yếu tố cần xem xét khi lựa chọn AWS Region đích cho hoạt động sao chép, bao gồm yêu cầu tuân thủ, độ trễ, chi phí lưu trữ, chi phí truyền dữ liệu, mức độ sẵn sàng dịch vụ và khả năng khôi phục sau sự cố.<br> - Thực hành tạo Destination Bucket mới theo mẫu `aws-first-cloud-ai-journey-xxxx-cross` tại Region N. Virginia (`us-east-1`), trong khi Source Bucket được đặt tại Singapore (`ap-southeast-1`).<br> - Lựa chọn Bucket nguồn đã tạo ở các bước trước và tải lại dữ liệu website lên Bucket nguồn theo hướng dẫn Workshop vì các Objects đã được di chuyển sang Bucket khác ở phần Move Objects.<br> - Truy cập Management → Replication rules trên Source Bucket và lựa chọn Create replication rule để tạo quy tắc sao chép dữ liệu.<br> - Đặt tên Replication Rule là `PrimaryToSecondary`, bật trạng thái Enabled và lựa chọn Apply to all objects in the bucket để áp dụng quy tắc cho toàn bộ Objects thuộc phạm vi Bucket.<br> - Trong phần Destination, lựa chọn Choose a bucket in this account để sao chép dữ liệu sang một Bucket khác trong cùng AWS Account.<br> - Sử dụng Browse S3 để lựa chọn Destination Bucket có hậu tố `-cross` tại Region N. Virginia (`us-east-1`).<br> - Thực hiện bật Bucket Versioning cho Destination Bucket theo yêu cầu của CRR.<br> - Trong mục IAM Role, lựa chọn Create new role để AWS tạo IAM Role và cấp các quyền cần thiết cho quá trình sao chép dữ liệu.<br> - Giữ các thiết lập còn lại theo mặc định, lưu Replication Rule và lựa chọn No, do not replicate existing objects để không sao chép các Objects đã tồn tại trước đó.<br> - Truy cập Destination Bucket tại Region N. Virginia và kiểm tra danh sách Objects ban đầu trước khi thực hiện thao tác tải dữ liệu mới lên Bucket nguồn.<br> - Thực hành tải một tệp hình ảnh mới trong thư mục `images` lên Source Bucket bằng chức năng Upload để kiểm tra hoạt động của Replication Rule.<br> - Truy cập lại Destination Bucket, làm mới trang và kiểm tra sự xuất hiện của tệp hình ảnh vừa tải lên sau khi quá trình sao chép hoàn tất.<br> - Tìm hiểu và tổng hợp các nguyên tắc bảo mật Amazon S3 trong phần Notes & Best Practices, bao gồm:<br>&nbsp;&nbsp;+ Duy trì Block Public Access ở trạng thái Enabled trong môi trường Production.<br>&nbsp;&nbsp;+ Ưu tiên sử dụng CloudFront kết hợp Origin Access Control (OAC) thay vì công khai trực tiếp S3 Bucket.<br>&nbsp;&nbsp;+ Sử dụng Bucket Policies để kiểm soát quyền truy cập một cách chi tiết.<br>&nbsp;&nbsp;+ Bật mã hóa mặc định SSE-S3 hoặc SSE-KMS, lựa chọn phương thức mã hóa phù hợp với mức độ nhạy cảm của dữ liệu.<br> - Tìm hiểu các nguyên tắc tối ưu hiệu năng, bao gồm cấu hình CloudFront Cache Behaviors, TTL, Compression, HTTP/2, IPv6, S3 Transfer Acceleration và Multipart Upload đối với các tệp có dung lượng lớn hơn 100 MB.<br> - Tìm hiểu các phương pháp tối ưu chi phí, bao gồm sử dụng S3 Intelligent-Tiering, Lifecycle Policies, S3 Storage Lens, quản lý các phiên bản cũ và theo dõi chi phí truyền dữ liệu.<br> - Tìm hiểu các lỗi thường gặp khi sử dụng Amazon S3 và CloudFront, đặc biệt là lỗi 403 Forbidden do cấu hình Block Public Access, Bucket Policy hoặc quyền truy cập CloudFront chưa chính xác.<br> - Phân biệt S3 Website Endpoint và S3 Bucket Endpoint, hiểu được sự khác nhau về khả năng hỗ trợ Static Website Hosting, HTTPS, OAC và OAI.<br> - Tìm hiểu vấn đề Cross-Origin Resource Sharing (CORS), nguyên nhân trình duyệt chặn yêu cầu giữa các nguồn khác nhau và cách cấu hình CORS phù hợp với nhu cầu truy cập.<br> - Thực hành dọn dẹp các tài nguyên sau Workshop bằng cách truy cập Amazon S3, lựa chọn các Bucket liên quan, sử dụng Empty để xóa toàn bộ Objects trước khi thực hiện Delete bucket.<br> - Thực hành dọn dẹp CloudFront Distribution bằng cách truy cập Amazon CloudFront, chọn Distribution đã tạo, thực hiện Disable và chờ hoàn tất quá trình vô hiệu hóa trước khi lựa chọn Delete.<br> - Kiểm tra lại danh sách S3 Bucket và CloudFront Distribution sau khi dọn dẹp để đảm bảo các tài nguyên thử nghiệm không còn được sử dụng và hạn chế chi phí phát sinh. | 13/11/2026 | 13/11/2026 | [Start With Amazon S3](https://000057.awsfcaj.com/)<br>[Replication Object Multi Region](https://000057.awsfcaj.com/10-s3ccr/)<br>[Clean Up Resources](https://000057.awsfcaj.com/11-cleanup/)<br>[Notes & Best Practices](https://000057.awsfcaj.com/12-notes/) |

### Kết quả đạt được trong tuần 6:

- Nắm được tổng quan về Amazon Simple Storage Service (Amazon S3), hiểu được vai trò của dịch vụ lưu trữ đối tượng trong AWS Cloud và những lợi ích về khả năng mở rộng, tính sẵn sàng, độ bền, bảo mật và hiệu quả chi phí.

- Hiểu được cấu trúc lưu trữ của Amazon S3 và phân biệt được hai thành phần cơ bản:
  - **S3 Bucket:** Vùng chứa cấp cao nhất được sử dụng để lưu trữ và tổ chức các đối tượng dữ liệu. Mỗi Bucket có tên duy nhất trên toàn cầu và thuộc một AWS Region cụ thể.
  - **S3 Object:** Đối tượng dữ liệu thực tế được lưu trữ bên trong Bucket, bao gồm nội dung dữ liệu, Object Key và các thông tin Metadata liên quan.

- Nắm được các lớp lưu trữ Amazon S3 và mục đích sử dụng của từng loại:
  - **S3 Standard:** Phù hợp với dữ liệu được truy cập thường xuyên.
  - **S3 Intelligent-Tiering:** Tự động tối ưu lớp lưu trữ theo mức độ truy cập dữ liệu.
  - **S3 Standard-IA:** Phù hợp với dữ liệu ít được truy cập nhưng vẫn cần khả năng truy xuất nhanh.
  - **S3 Glacier:** Phù hợp với nhu cầu lưu trữ và lưu trữ dài hạn, yêu cầu thời gian truy xuất tùy theo cấu hình.
  - **S3 Glacier Deep Archive:** Phù hợp với dữ liệu cần lưu trữ dài hạn và có tần suất truy xuất rất thấp.

- Hiểu được các tính năng quan trọng của Amazon S3 như Encryption, Access Control, Versioning, Lifecycle Management, Cross-Region Replication và S3 Storage Lens.

- Có kinh nghiệm thực hành tạo và cấu hình Amazon S3 Bucket thông qua AWS Management Console, lựa chọn AWS Region, thiết lập tên Bucket duy nhất và cấu hình các tùy chọn bảo mật mặc định.

- Hiểu được các thiết lập quan trọng khi khởi tạo S3 Bucket:
  - Object Ownership với tùy chọn ACLs disabled (recommended).
  - Block all public access được bật mặc định.
  - Bucket Versioning được tắt trong bước khởi tạo.
  - Default Encryption sử dụng SSE-S3.
  - AWS Region được lựa chọn phù hợp với nhu cầu lưu trữ dữ liệu.

- Thực hành tải mã nguồn website mẫu từ GitHub lên Amazon S3, biết cách sử dụng chức năng Upload để lưu trữ các tệp HTML, CSS, JavaScript, hình ảnh và các tài nguyên website dưới dạng Objects trong Bucket.

- Nắm được nguyên lý hoạt động của Static Website Hosting trên Amazon S3 và thực hành triển khai website tĩnh thông qua:
  - Kích hoạt Static Website Hosting trong mục Properties.
  - Lựa chọn loại hình Host a static website.
  - Thiết lập `index.html` làm trang mặc định.
  - Cấu hình `error.html` làm trang lỗi tùy chọn.
  - Kiểm tra Website Endpoint sau khi bật tính năng.

- Hiểu được sự khác nhau giữa Website Endpoint và S3 Bucket Endpoint, đặc biệt là khả năng phân phối nội dung website tĩnh thông qua HTTP và sự cần thiết của CloudFront khi muốn hỗ trợ HTTPS.

- Hiểu được cơ chế quản lý quyền truy cập của Amazon S3, phân biệt quyền truy cập cấp độ Bucket và Object, đồng thời nhận biết vai trò của ACLs, Bucket Policies và IAM Policies.

- Có kinh nghiệm thực hành cấu hình quyền truy cập công khai cho các đối tượng website bằng cách:
  - Thay đổi Block all public access theo yêu cầu bài thực hành.
  - Bật ACLs trong Object Ownership.
  - Chuyển sang tùy chọn Bucket owner preferred.
  - Sử dụng Make public using ACL để cấp quyền đọc công khai cho các Objects được lựa chọn.
  - Kiểm tra quyền truy cập của các tệp tin website sau khi cấu hình.

- Thực hành kiểm tra hoạt động của Static Website thông qua Website Endpoint trên trình duyệt, xác nhận khả năng hiển thị giao diện website và sử dụng Developer Tools để quan sát thời gian tải trang trước khi tích hợp CloudFront.

- Nắm được vai trò của Amazon CloudFront trong việc phân phối nội dung thông qua Content Delivery Network (CDN), tận dụng hệ thống Edge Locations để giảm độ trễ và cải thiện tốc độ truy cập của người dùng.

- Thực hành tạo CloudFront Distribution và tích hợp với S3 Bucket làm Origin, bao gồm:
  - Tạo Distribution mới trên Amazon CloudFront.
  - Lựa chọn gói phù hợp với mục đích thực hành.
  - Lựa chọn Amazon S3 làm Origin Type.
  - Chọn S3 Bucket làm nguồn cung cấp nội dung.
  - Cấu hình Default root object là `index.html`.
  - Cập nhật Bucket Policy được CloudFront cung cấp vào S3 Bucket.
  - Theo dõi trạng thái triển khai Distribution.

- Hiểu được cách kết hợp Amazon S3 với CloudFront để phân phối website mà không cần công khai trực tiếp S3 Bucket; thực hành bật lại Block all public access sau khi hoàn tất bước kiểm tra website công khai trực tiếp trên S3.

- Có kinh nghiệm kiểm tra website thông qua CloudFront Distribution Domain Name, biết cách xác định thời gian tải trang qua Developer Tools → Network và so sánh với kết quả truy cập trực tiếp thông qua S3 Website Endpoint.

- Hiểu được cách kiểm tra Response Headers và thuộc tính `x-amz-cf-pop` nhằm xác định Point of Presence (PoP) đang cung cấp nội dung website; nhận biết ví dụ `SGN50-P2` tương ứng với Ho Chi Minh City trong Workshop.

- Nhận thức được lợi ích của CloudFront trong việc phân phối nội dung từ Edge Location gần người dùng, giảm độ trễ, tăng tốc độ tải trang và cải thiện trải nghiệm truy cập website.

- Nắm được chức năng Amazon S3 Bucket Versioning, hiểu được khả năng lưu giữ nhiều phiên bản của cùng một Object và hỗ trợ khôi phục dữ liệu khi xảy ra ghi đè hoặc xóa nhầm.

- Phân biệt được ba trạng thái Versioning gồm:
  - **Unversioned:** Trạng thái mặc định, chưa bật quản lý phiên bản.
  - **Versioning-enabled:** Cho phép tạo phiên bản mới mỗi khi Object được tải lên hoặc thay đổi.
  - **Versioning-suspended:** Ngừng tạo các phiên bản mới nhưng vẫn duy trì những phiên bản đã tồn tại.

- Hiểu được cơ chế Version ID và Delete Marker trong quá trình quản lý phiên bản đối tượng; nhận thức được lợi ích của Versioning đối với bảo vệ dữ liệu và theo dõi lịch sử thay đổi.

- Có kinh nghiệm thực hành bật Versioning, chỉnh sửa nội dung tệp `index.html`, tải phiên bản mới lên S3 và sử dụng Show versions để kiểm tra hai phiên bản của cùng một Object.

- Nhận thức được ảnh hưởng của Versioning đến dung lượng lưu trữ và chi phí AWS, hiểu được mỗi phiên bản được tính dung lượng lưu trữ riêng và sự cần thiết của việc sử dụng Lifecycle Policies để quản lý những phiên bản cũ không còn cần thiết.

- Thực hành di chuyển Objects giữa các S3 Bucket bằng chức năng Actions → Move, biết cách lựa chọn Bucket nguồn, Bucket đích, tính toán tổng dung lượng dữ liệu và kiểm tra kết quả sau khi hoàn tất thao tác.

- Hiểu được lợi ích của việc di chuyển Objects trong quá trình tổ chức, phân loại và quản lý dữ liệu giữa các S3 Bucket, đồng thời nắm được cách kiểm tra số lượng và dung lượng đối tượng trước và sau khi di chuyển.

- Nắm được tổng quan về Amazon S3 Cross-Region Replication (CRR), hiểu được khả năng tự động sao chép Objects giữa các Bucket thuộc những AWS Region khác nhau nhằm tăng cường khả năng dự phòng và khôi phục dữ liệu.

- Hiểu được các lợi ích chính của Cross-Region Replication:
  - **Disaster Recovery:** Hỗ trợ bảo vệ dữ liệu khi xảy ra sự cố ở một AWS Region.
  - **Compliance:** Hỗ trợ đáp ứng các yêu cầu về phân phối và lưu trữ dữ liệu theo khu vực địa lý.
  - **Latency Reduction:** Hỗ trợ phân phối dữ liệu từ khu vực phù hợp với người dùng.
  - **Data Sovereignty:** Hỗ trợ duy trì bản sao dữ liệu tại các địa điểm địa lý cụ thể.
  - **Operational Excellence:** Góp phần duy trì hoạt động liên tục của hệ thống.

- Nắm được các điều kiện cần thiết khi cấu hình CRR:
  - Bật Versioning cho cả Source Bucket và Destination Bucket.
  - Tạo và kích hoạt Replication Rule.
  - Lựa chọn phạm vi Objects cần sao chép.
  - Sử dụng IAM Role để cấp quyền cho quá trình sao chép.
  - Xác định AWS Region và Destination Bucket phù hợp.

- Có kinh nghiệm thực hành cấu hình Cross-Region Replication từ Singapore (`ap-southeast-1`) sang N. Virginia (`us-east-1`), tạo Replication Rule `PrimaryToSecondary` và lựa chọn Apply to all objects in the bucket.

- Hiểu được cách sử dụng IAM Role trong việc cấp quyền cho Amazon S3 thực hiện sao chép dữ liệu giữa các Bucket, đồng thời nhận biết lựa chọn No, do not replicate existing objects trong bài thực hành.

- Thực hành tải một tệp hình ảnh mới lên Source Bucket, truy cập Destination Bucket và kiểm tra kết quả sau khi quá trình replication hoàn tất.

- Nhận thức được tầm quan trọng của CRR đối với Disaster Recovery, Geographic Redundancy, Data Availability và khả năng bảo vệ dữ liệu khi có sự cố tại một AWS Region.

- Nắm được các nguyên tắc bảo mật Amazon S3 trong môi trường thực tế, bao gồm:
  - Duy trì Block Public Access ở trạng thái Enabled trong môi trường Production.
  - Ưu tiên sử dụng CloudFront kết hợp Origin Access Control (OAC) thay vì công khai trực tiếp S3 Bucket.
  - Sử dụng Bucket Policies để kiểm soát quyền truy cập một cách chi tiết.
  - Bật mã hóa mặc định bằng SSE-S3 hoặc SSE-KMS.
  - Lựa chọn phương thức mã hóa phù hợp với mức độ nhạy cảm của dữ liệu.

- Tìm hiểu các nguyên tắc tối ưu hiệu năng Amazon S3 và CloudFront, bao gồm cấu hình Cache Behaviors, TTL, Compression, HTTP/2, IPv6, S3 Transfer Acceleration và Multipart Upload đối với các tệp có dung lượng lớn hơn 100 MB.

- Nắm được một số phương pháp tối ưu chi phí AWS:
  - Sử dụng S3 Intelligent-Tiering khi chưa xác định rõ tần suất truy cập dữ liệu.
  - Thiết lập Lifecycle Policies để tự động chuyển đổi Storage Classes.
  - Sử dụng S3 Storage Lens để theo dõi mức sử dụng và chi phí lưu trữ.
  - Quản lý và xóa các phiên bản Object cũ không còn cần thiết.
  - Theo dõi chi phí truyền dữ liệu và sử dụng CloudFront phù hợp.

- Tìm hiểu các lỗi thường gặp khi triển khai Amazon S3 và CloudFront, đặc biệt là lỗi 403 Forbidden do Block Public Access, Bucket Policy hoặc quyền truy cập CloudFront chưa được cấu hình chính xác.

- Phân biệt được S3 Website Endpoint và S3 Bucket Endpoint, hiểu được sự khác nhau về khả năng hỗ trợ Static Website Hosting, OAC và OAI; nhận thức được S3 Bucket Endpoint phù hợp hơn khi tích hợp CloudFront với OAC trong môi trường cần bảo mật.

- Hiểu được vấn đề Cross-Origin Resource Sharing (CORS), nguyên nhân trình duyệt có thể chặn các yêu cầu giữa những nguồn khác nhau và vai trò của cấu hình CORS trong việc kiểm soát quyền truy cập tài nguyên.

- Nắm được quy trình dọn dẹp tài nguyên sau Workshop, bao gồm:
  - Làm trống các S3 Bucket liên quan bằng chức năng Empty.
  - Xóa các S3 Bucket thử nghiệm sau khi đã xóa dữ liệu bên trong.
  - Disable CloudFront Distribution và chờ quá trình vô hiệu hóa hoàn tất.
  - Delete CloudFront Distribution sau khi không còn sử dụng.

- Nhận thức được tầm quan trọng của việc quản lý tài nguyên, dữ liệu và chi phí AWS, đặc biệt đối với Amazon S3 và CloudFront; hiểu được cần kiểm tra các Bucket, Objects, phiên bản dữ liệu và Distribution còn tồn tại sau khi hoàn thành bài thực hành.

- Tổng hợp được kiến thức và kinh nghiệm thực hành về Amazon S3 trong việc lưu trữ đối tượng, triển khai website tĩnh, phân phối nội dung thông qua CloudFront, quản lý phiên bản, di chuyển dữ liệu và sao chép dữ liệu giữa các Region trên AWS Cloud.

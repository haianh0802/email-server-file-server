
# File Server là gì?
File Server (hay máy chủ tập tin) là một máy chủ được kết nối mạng có nhiệm vụ cung cấp không gian, địa điểm để lưu trữ và chia sẻ dữ liệu như văn bản, hình ảnh, âm thanh, video. Trong doanh nghiệp, tập tin máy chủ được dùng để lưu trữ và quản lý dữ liệu. Cụ thể, doanh nghiệp sẽ quản lý quyền truy cập và sử dụng dữ liệu của từng nhân viên từng phòng ban hoặc từng nhóm làm việc.
# Những lợi ích của file server
Một file server có thể là máy chủ chuyên dụng hoặc không chuyên dụng. Các máy chủ chuyên dụng thường được dùng cho các ứng dụng trong doanh nghiệp, vì chúng cung cấp khả năng truy cập dữ liệu nhanh hơn và cung cấp dung lượng lưu trữ cao hơn các hệ thống không chuyên dụng.

Như vậy, tất cả các máy tính đều có thể trở thành một máy chủ và hoạt động như một file server. Một số lợi ích mà file server mang lại cho doanh nghiệp gồm:

### Dễ dàng quản lý từ xa
Truy cập thông tin từ xa đôi lúc sẽ trở nên rất quan trọng trong nhiều tình huống. Một ví dụ có thể là trích xuất dữ liệu từ một nhánh từ xa. Ngay cả khi một nhân viên không có mặt trong công ty, bạn vẫn có thể truy cập dữ liệu của họ thông qua Máy chủ tệp.

### Hỗ trợ đa giao thức chia sẻ file trên các nền tảng thiết bị khác nhau
Một File server cho phép người dùng chia sẻ thông tin qua mạng mà không cần phải chuyển tập tin thông qua bằng đĩa mềm hoặc một số thiết bị lưu trữ ngoài khác.

Điểm nổi bật của file server là hỗ trợ đầy đủ các giao thức AFP, FTP, NFS, SMB, WebDAV, HTTP. Nhờ vậy, các dữ liệu lưu trữ trên Synology được truy cập mọi lúc, mọi nơi từ các máy tính Windows, Mac, Linux.

### Bảo mật và sao lưu dữ liệu
Thông thường, các doanh nghiệp nhỏ sẽ lưu trữ tập tin trên trên các ổ đĩa cục bộ, tuy nhiên khi các ổ cứng đó bị lỗi sẽ dẫn đến những vấn đề vô cùng nghiêm trọng như mất hết dữ liệu,..Vì vậy doanh nghiệp cần phải sử dụng file server để tạo bản sao lưu khi cần.

Mỗi User, Admin,HR,Account,Team Leader….ở doanh nghệp điều được phân cấp quyền hạn chặt chẽ đảm bảo tính bảo mật và an toàn dữ liệu công ty. Ngoài ra, công nghệ RAID giảm thiểu tối đa khả năng mất dữ liệu do hỏng hóc ổ cứng thường gặp

### Khả năng phục hồi dữ liệu dễ dàng
Có nhiều tính năng phục hồi dữ liệu có sẵn trong file server. Bạn có thể dễ dàng lấy các tập tin mà không có bất kỳ vấn đề, kể cả những tập tin vô tình bị xóa.

### Hỗ trợ giám sát nhân viên
File server còn cung cấp những tính năng có thể giúp bạn theo dõi những hoạt động của nhân viên. Bạn cũng có thể thông qua file server xem các trang web mà người dùng mạng của bạn đang truy cập để bảo vệ khỏi các tệp tải xuống độc hại có thể tạo ra nhiều sự tàn phá.

Ngoài ra, một số ưu điểm của file server cần được kể đến như:

- Chỉ với mức phí đầu tư về lưu trữ,bảo mật, backup cho một Server
- Dữ liệu được quản lý một cách có hệ thống và tập trung.
- Việc phân bổ dữ liệu theo phòng ban, Project được sắp xếp logic hợp lý
- Việc tham chiếu, kiểm tra tìm kiếm dữ liệu dễ dàng
- Các cấp lãnh đạo,trưởng phòng có thể theo dõi tiến độ công việc 1 cách dễ dàng
## File server gồm các loại nào?
File server được phân thành 4 loại theo phương thức truy cập:

- FTP: File Transfer Protocol
- HTTP: Hypertext Transfer Protocol
- NFS: Network File System – Chủ yếu là cho UNIX, hệ thống tương tự UNIX
- SMB: CIFS/Server Message Block – Dùng cho Windows hoặc UNIX

# Cấu trúc của file server
### Storage
Đây là chức năng quan trọng nhất trong File server. Hiện nay, rất nhiều công nghệ được phát triển cho phép vận hành ổ đĩa theo nhóm và tạo thành 1 Disk arry. Disk arry được dùng để chứa bộ nhớ tạm, có chức năng hiện đại hơn như ảo hóa lưu trữ hay RAID. Nhờ các yếu tố dự phòng ngoài RAID mà Disk arry cũng giúp nâng cao độ sẵn sàng.

### Network – attached storage
Network – attached storage được kết nối với mạng máy tính, nó có khả năng lưu trữ dữ liệu cấp độ tập tin. Cũng nhờ vậy mà nhóm máy khách (client) không đồng nhất vẫn có thể truy cập dữ liệu.

Hệ thống Network – attached storage bao gồm các thiết bị kết nối mạng với một hoặc nhiều ổ cứng, được xếp thành các RAID arry hoặc Storage container dự phòng. Network – attached storage cho phép quyền truy cập file, dùng các giao thức như SMB/CIFS, NFS, AFP chia sẻ file qua mạng.


# Cách thức hoạt động của file server
### Nguyên lý hoạt động của file server
Đầu tiên, Các dữ liệu này có thể được truy cập bởi các workstation (máy trạm). Workstation này có thể kết nối được tới máy chủ khi các máy này chia sẻ quyền truy cập thông qua một mạng máy tính.

Sau đó, Server sẽ thực hiện vai trò của mình trong sơ đồ Client-server. Trong sơ đồ này, các khách hàng (client) là các máy trạm sử dụng kho lưu trữ.
Một File server thường không thực hiện bất kỳ phép tính toán hay chạy chương trình nào thay mặt cho khách hàng. Nó được thiết kế chủ yếu để cho phép lưu trữ nhanh chóng và lấy dữ liệu, các tính toán được thực hiện bởi các máy trạm.
![image](https://user-images.githubusercontent.com/101684058/162874523-0f6b2727-00f4-46d0-8294-3b7548f7a0fb.png)

#Các hình thức file server:
Nói đến chia sẻ dữ liệu tập trung hay còn gọi là file server thì chúng ta có nhiều hình thái khác nhau như :
+ Xây dựng máy chủ chạy trên nền tảng Linux or Windows Server

+ Hệ thống NAS

+ Giải pháp SAN

# Những lưu ý khi lựa chọn file server
File server là nơi lưu trữ, quản lý và chia sẻ dữ liệu chính của một doanh nghiệp, vì vậy khi lựa chọn file server cần lưu ý những vấn đề sau:

- An toàn: Để đảm bảo an toàn cho tài liệu lưu trữ, bạn có thể áp dụng một số phương pháp như xây dựng cơ sở hạ tầng đạt chuẩn hoặc thực hiện các giải pháp khác.Hạ tầng: Cơ sở hạ tầng để đặt máy chủ cơ sở dữ liệu phải đáp ứng đầy đủ các yêu cầu tiêu chuẩn hoạt động. Ngoài ra phải đảm bảo File Server trực tuyến trong suốt thời gian công ty hoạt động hành chính hoặc 24/24 tùy từng trường hợp.
- Giải pháp: bạn cần đảm bảo file server lúc nào cũng trong trạng thái sẵn sàng đối phó các trường hợp rủi ro có thể gây ra việc mất mát dữ liệu như: hỏng hóc phần cứng ( ổ cứng, raid lỗi…), sự cố cháy nổ máy chủ, shock điện…
- Tiện ích: Tiện ích nằm ở khả năng mở rộng lưu trữ, thao tác đơn giản không đòi hỏi nhiều chuyên môn và không tốn nhiều thời gian của người sử dụng
- Bảo mật: Đảm bảo dữ liệu chỉ được chia sẻ cho những đối tượng được cấp quyền trong hệ thống.
- Tốc độ truyền tải: Tùy thuộc vào nhu cầu của người dùng.


# NAS so với SAN: 7 sự khác biệt lớn
#### 1) Fabrics (Kết cấu mạng). 
 NAS sử dụng mạng TCP/IP, phổ biến nhất là Ethernet. Các SAN truyền thống thường chạy trên các mạng fibre channel (FC) tốc độ cao, mặc dù nhiều SAN đang sử dụng fabric dựa trên IP vì chi phí và độ phức tạp của FC. Hiệu suất cao vẫn là một yêu cầu SAN và các giao thức fabric dựa trên flash đang giúp thu hẹp khoảng cách giữa tốc độ FC và IP chậm hơn.

#### 2) Xử lý dữ liệu.
Hai kiến trúc lưu trữ xử lý dữ liệu khác nhau: NAS xử lý dữ liệu dựa trên file và SAN xử lý dữ liệu khối. Câu chuyện không hoàn toàn đơn giản như tất nhiên: NAS có thể hoạt động với không gian tên toàn cầu và SAN có quyền truy cập vào hệ thống file SAN chuyên dụng. Một không gian tên toàn cầu tổng hợp nhiều hệ thống file NAS để trình bày một khung nhìn hợp nhất. Hệ thống tập tin SAN cho phép các máy chủ chia sẻ tập tin. Trong kiến ​​trúc SAN, mỗi máy chủ duy trì một LUN chuyên dụng, không chia sẻ. Hệ thống file SAN cho phép các máy chủ chia sẻ dữ liệu một cách an toàn bằng cách cung cấp quyền truy cập cấp file vào các máy chủ trên cùng LUN.

#### 3) Giao thức. 
NAS kết nối trực tiếp với mạng Ethernet thông qua cáp vào bộ chuyển mạch Ethernet. NAS có thể sử dụng một số giao thức để kết nối với các máy chủ bao gồm NFS, SMB / CIFS và HTTP. Về phía SAN, các máy chủ liên lạc với các thiết bị ổ đĩa SAN bằng giao thức SCSI. Mạng được hình thành bằng cách sử dụng các loại fabric SAS / SATA hoặc ánh xạ các lớp sang các giao thức khác, chẳng hạn như Giao thức Kênh sợi (FCP) ánh xạ SCSI qua Kênh sợi quang hoặc iSCSI ánh xạ SCSI qua TCP/IP.

#### 4) Hiệu suất. 
SAN là những người thực hiện cao hơn cho các môi trường cần lưu lượng tốc độ cao như cơ sở dữ liệu giao dịch cao và các trang web thương mại điện tử. NAS thường có thông lượng thấp hơn và độ trễ cao hơn do lớp hệ thống file chậm hơn, nhưng các mạng tốc độ cao có thể bù đắp cho tổn thất hiệu năng trong NAS.

#### 5) Khả năng mở rộng. 
Các thiết bị NAS cấp và đầu vào không có khả năng mở rộng cao, nhưng các hệ thống NAS cao cấp có quy mô đến petabyte bằng cách sử dụng các cụm hoặc các nút mở rộng quy mô. Ngược lại, khả năng mở rộng là một động lực chính để mua SAN. Kiến trúc mạng của nó cho phép quản trị viên mở rộng hiệu suất và dung lượng trong các cấu hình mở rộng hoặc mở rộng.

#### 6) Giá cả. 
Mặc dù một NAS cao cấp sẽ có giá cao hơn SAN cấp nhập cảnh, nhưng nhìn chung NAS ít tốn kém hơn để mua và bảo trì. Các thiết bị NAS được coi là thiết bị và có ít thành phần quản lý phần cứng và phần mềm hơn mạng lưu trữ. Chi phí hành chính cũng tính vào phương trình. SAN phức tạp hơn để quản lý với FC SAN trên đỉnh của sự phức tạp. Một nguyên tắc nhỏ là tính toán từ 10 đến 20 lần chi phí mua hàng như một tính toán bảo trì hàng năm.

#### 7) Dễ quản lý. 
Trong một so sánh một-một, NAS thắng cuộc thi quản lý dễ dàng. Thiết bị dễ dàng cắm vào mạng LAN và cung cấp giao diện quản lý đơn giản. SAN yêu cầu nhiều thời gian quản trị hơn thiết bị NAS. Triển khai thường yêu cầu thực hiện các thay đổi vật lý cho trung tâm dữ liệu và quản lý liên tục thường yêu cầu quản trị viên chuyên ngành. Ngoại lệ cho đối số SAN-is-hard là nhiều thiết bị NAS không chia sẻ bảng điều khiển quản lý chung.

# SAN và NAS kết hợp
SAN / NAS hợp nhất (hoặc đa giao thức) kết hợp file và khối lưu trữ vào một hệ thống lưu trữ duy nhất. Các hệ thống thống nhất này hỗ trợ tối đa bốn giao thức. Bộ điều khiển lưu trữ phân bổ lưu trữ vật lý để xử lý NAS hoặc SAN.

Chúng phổ biến cho các doanh nghiệp tầm trung, những người cần cả SAN và NAS, nhưng thiếu không gian trung tâm dữ liệu và quản trị viên chuyên biệt cho các hệ thống riêng biệt. SAN / NAS hội tụ là một phần nhỏ của thị trường so với các triển khai khác biệt nhưng cho thấy sự tăng trưởng ổn định.

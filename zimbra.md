### Bước 1: Tạo các bản ghi mail

![image](https://user-images.githubusercontent.com/101684058/164392562-e07e845c-0ed6-499a-91b9-3027257f0640.png)

### Bước 2:  Kiểm tra và cập nhật hệ thống
Bước đầu tiên bạn cần kiểm tra SELINUX xem có đang bật không, nếu đang bật thì bạn tắt đi.

`# vi /etc/selinux/config`

![image](https://user-images.githubusercontent.com/101684058/163749135-6228c124-54c1-4fb1-b7c4-17f920e0ff3f.png)

Thực hiện stop postfix và remove postfix.

Postfix là một phầm mềm nguồn mở được dùng để gửi mail (Mail Transfer Agent-MTA). Được phát hành bởi IBM với mục tiêu thay thế trình gửi mail phổ biến là sendmail. Nó được trang bị trên hệ điều hành do đó bạn hãy xoá bỏ để sử dụng dịch vụ riêng của Zimbra.

`# systemctl stop postfix`

`# yum remove postfix -y`

![image](https://user-images.githubusercontent.com/101684058/163752686-9d1f68a0-0447-437d-8810-0c56b70a74e7.png)

Sau đó bạn cập nhật hệ thống bằng lệnh sau và reboot lại máy chủ để áp dụng

`# yum update -y ; reboot`

### Bước 3: Kiểm tra và set hostname
Bạn thực hiện kiểm tra hostname và set lại hostname tương ứng

`# hostnamectl set-hostname mail.haianh82.xyz`

`# exec bash`


![image](https://user-images.githubusercontent.com/101684058/163755163-88f1ecb0-9f74-4450-a260-6b9b2b1a53c6.png)

Sau khi set hostname xong bạn thêm dòng sau vào file hosts
Thay đổi ip
`nano /etc/hosts`

![image](https://user-images.githubusercontent.com/101684058/164372862-1a06a17d-6a37-4176-b678-9d50e8109007.png)

### Bước 4: Cài đặt Zimbra
Thực hiện chạy lệnh sau để install Zimbra & ZCS dependencies

`yum install unzip net-tools sysstat openssh-clients perl-core libaio nmap-ncat libstdc++.so.6 wget -y`

Download Zimbra và cài đặt. Và bạn cần tạo một thư mục zimbra để cài vào đó
`[root@mail ~]# mkdir zimbra && cd zimbra`

`[root@mail zimbra]# wget https://files.zimbra.com/downloads/8.8.15_GA/zcs-8.8.15_GA_3869.RHEL7_64.20190918004220.tgz --no-check-certificate[root@mail ~]# mkdir zimbra && cd zimbra`

![image](https://user-images.githubusercontent.com/101684058/163755785-1b086f4b-4852-44e7-b75c-8dddc3e22f3b.png)

Sau khi download về hoàn tất bạn tiến hành giải nén file ra

`tar zxpvf zcs*.tgz`

Truy cập vào thư mục vừa giải nén và chạy lệnh ./install

`root@mail zimbra]# cd zcs* && ./install.sh`


![image](https://user-images.githubusercontent.com/101684058/163981870-960bd8b5-ed2c-4ec2-a670-7761fa26b6bc.png)


Khi cài đặt xong bạn hãy khởi động lại dịch vụ Zimbra bằng lệnh sau

`[root@mail ~]# su zimbra`

`[zimbra@mail root]$ zmcontrol restart`

![image](https://user-images.githubusercontent.com/101684058/164389586-7a641788-4a03-460b-baa9-b6da997dfc6b.png)

## Bước 5: Mở Port Firewall
Như vậy là đã hoàn tất rồi nhé, nếu máy chủ bạn có cài Firewall bạn cần mở các port sau ra để email hoạt động

Dưới đây là các Port bạn cần mở

`firewall-cmd --permanent --add-port={25,80,110,143,443,465,587,993,995,5222,5223,9071,7071}/tcp`

`firewall-cmd --reload`

![image](https://user-images.githubusercontent.com/101684058/164390332-84efd190-0366-4c9b-914c-c3b8f0c46a1f.png)

Sau đó bạn truy cập admin zimbra bằng IP:port qua giao thức https nhé

VD: https://192.168.154.128:7071/zimbraAdmin

![image](https://user-images.githubusercontent.com/101684058/164392395-7616d8ca-da0f-49e0-b619-08d4c0de827e.png)

Giao zimbra

![image](https://user-images.githubusercontent.com/101684058/164392479-63886c88-0088-400d-944b-cfa6ac8a248b.png)

# Một số thao tác 
### Tạo tài khoản mail trên Zimbra

Truy cập vào trang quản lý

![image](https://user-images.githubusercontent.com/101684058/164401547-9d36f45c-1283-44e5-a0a9-76c697ab35ee.png)

Sau đó bạn để ý ở góc phải trên cùng. Hãy click vào nơi minh khoanh và chọn MỚI để tạo mới.

![image](https://user-images.githubusercontent.com/101684058/164402672-c1b655d0-43af-45a7-9283-2be0204ed734.png)

giao diện tạo tài khoản xuất hiện. Bạn hãy nhập vào các thông tin cá nhân để tạo.

![image](https://user-images.githubusercontent.com/101684058/164403565-6bb1c679-6cfc-46a7-ba36-2ed1027bd788.png)

Tiêp theo bạn kéo thanh cuốn bên tay phải xuống dưới nhập Passwd User và nhập lại Passwd. Sau khi điền chính xác thì click finish

![image](https://user-images.githubusercontent.com/101684058/164403726-a8e61b92-ac79-4214-91e2-67af39a3be69.png)

Bây giờ bạn sẽ thấy các tài khoản hiện có ở đây.

![image](https://user-images.githubusercontent.com/101684058/164403831-ae4df40b-1af4-4e6a-9abb-77e4d3b8d150.png)


### Đăng nhập vào Webmail
Sau khi tạo xong tài khoản. Bạn hãy truy cập vào https://your-my-ip hoặc là https://my-domain để đăng nhập vào trang webmail

![image](https://user-images.githubusercontent.com/101684058/164416945-afcee308-5f16-4865-a443-4c29127be269.png)

![image](https://user-images.githubusercontent.com/101684058/164417204-c562f7d7-dd7c-4a02-abd1-1cf20eb7384c.png)

### Soạn và gửi Mail
Sau khi đã đăng nhập được vào webmail. Bạn hãy chọn Thư mới để bắt đầu soạn và gửi mail nhé.

![image](https://user-images.githubusercontent.com/101684058/164418068-7f337087-6671-4e96-9c04-4c45d8643dc7.png)


![image](https://user-images.githubusercontent.com/101684058/164430084-c23dd334-1a49-4531-8ed8-ca7ea7eb44e1.png)


![image](https://user-images.githubusercontent.com/101684058/164422818-0cc8b4da-4616-4912-804e-3aaae8293292.png)

![image](https://user-images.githubusercontent.com/101684058/164430672-885dfe0e-562f-4ae0-b4b5-af26bf56490c.png)

![image](https://user-images.githubusercontent.com/101684058/164430917-67b66a7d-2607-4aa1-b24a-e0b05ff58da4.png)

### Danh bạ

![image](https://user-images.githubusercontent.com/101684058/164432252-d1c9f1cf-d618-4a4a-8506-2711d0b8d9fb.png)

Tại đây bạn có thể điền các thông tin cá nhân như tên và địa chỉ Email v.v , sau khi hoàn tất điền bạn có thể nhấn Lưu để hoàn tất.

![image](https://user-images.githubusercontent.com/101684058/164434285-e49f7a37-3ce6-4c8d-9237-ae97ca47da0b.png)

![image](https://user-images.githubusercontent.com/101684058/164434330-732d23f8-9a4f-46b2-a069-5de366211c5e.png)

Sau khi có danh bạ bạn có thể thực hiện gửi mail và tìm kiếm danh bạ ngay trên phần soạn Mail.

### Lịch

![image](https://user-images.githubusercontent.com/101684058/164436320-9484ad0d-e117-4a31-8222-bf1529811e26.png)

![image](https://user-images.githubusercontent.com/101684058/164437674-f9017dc8-47f5-4b36-9184-a120dc102aa2.png)

### Công việc

Chọn công việc mới 

![image](https://user-images.githubusercontent.com/101684058/164627505-ac22d535-2148-4d07-956e-34a9dc3d1bd3.png)

Điền đầy đủ thông tin cần thiết

![image](https://user-images.githubusercontent.com/101684058/164627933-6d37cc52-a2e0-4973-851b-18e992bc31f1.png)

Thông báo nhắc nhở

![image](https://user-images.githubusercontent.com/101684058/164628258-93fae27b-558d-4524-89f1-86916f57124c.png)

### Cặp tài liệu

chọn thêm mới tài liệu

![image](https://user-images.githubusercontent.com/101684058/164628520-83ab76c3-6d38-4504-ba2e-aa7d9cd1dc24.png)

Điền thông tin tài liệu cần lưu trữ lại và bấm lưu 

![image](https://user-images.githubusercontent.com/101684058/164628853-1aed54fa-a462-4de7-945b-1ba850248c75.png)


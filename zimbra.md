### Bước 1: Tạo các bản ghi mail
![image](https://user-images.githubusercontent.com/101684058/163547615-d6b92d99-c6ab-46eb-876e-421a63ed2334.png)

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

![image](https://user-images.githubusercontent.com/101684058/163755375-410e2114-291e-4ee9-b62f-10d58aedc9dc.png)

### Bước 4: Cài đặt Zimbra
Thực hiện chạy lệnh sau để install Zimbra & ZCS dependencies

Tạo các bản ghi 
![image](https://user-images.githubusercontent.com/101684058/163547615-d6b92d99-c6ab-46eb-876e-421a63ed2334.png)


## Chuẩn bị môi trường cho việc cài đặt Zimbra
Cài đặt screen

` yum install screen -y`

Cài đặt hostname

`hostnamectl set-hostname mail.vhost.vn` 

Cấu hình lại files hosts

`echo 103.143.208.217 mail.vhost.vn  mail > /etc/hosts`

Cài đặt Extra Packages for Enterprise Linux

`yum install epel-release -y`

Gỡ bỏ postfix mặc định của CentOS 7.

Do Zimbra cũng sử dụng postfix vì vậy bạn nên disabled hoặc gỡ bỏ postfix mặc định của CentOS để tránh gặp lỗi sau này.

`yum remove postfix -y`

Cài đặt 1 số software khác hỗ trợ cho quá trình cài đặt.

`yum install wget unzip -y`

Cập nhật lại timzone của hệ thống.

`timedatectl set-timezone Asia/Ho_Chi_Minh`

Cấu hình lại nameserver của hệ thống để phân giải tên miền.

`echo "nameserver 8.8.8.8" >> /etc/resolv.conf`

Update lại hệ thống để đảm bảo máy chủ của bạn được cập nhật các bản vá mới nhất

`yum update -y`

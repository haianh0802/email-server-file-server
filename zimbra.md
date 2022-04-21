### Bước 1: Tạo các bản ghi mail

![image](https://user-images.githubusercontent.com/101684058/164128643-5f1b2282-987c-4416-b762-3da147176fa9.png)

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

![image](https://user-images.githubusercontent.com/101684058/164392479-63886c88-0088-400d-944b-cfa6ac8a248b.png)


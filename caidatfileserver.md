# Cách cài đặt File Server Resource Manager trong Windows Server 2019

Bước 1 - Vào Server Manager > Manage > Add Roles and Features > Next. Chọn Role-based or feature-based installation, rồi chọn Select a server from the server pool. Bấm Next.

Sau đó, tại danh sách, tìm File and Storage Services và mở rộng nó. Sau đó, mở rộng Files and iSCSI Services, chọn File Server Resource Manager và sau đó một cửa sổ sẽ mở ra.

![image](https://user-images.githubusercontent.com/101684058/163304798-1891e4cc-5b27-4a07-910d-575502b9be32.png)

Bước 2 - Nhấp vào Add features và sau đó bấm Next.

Bước 3 - Nhấp vào nút Next.

![image](https://user-images.githubusercontent.com/101684058/163304983-7ba8473c-ba34-46dd-b38e-9c7959806d96.png)

Bước 4 - Nhấp vào nút Install.
# Cách mở File Server Resource Manager
Bước 1 - Nhấp vào Server Manager > Tools > File Server Resource Manager.
![image](https://user-images.githubusercontent.com/101684058/163305226-787d4f68-b55b-4351-b0d9-030d9c5ac885.png)

Bước 2 - Trên bảng điều khiển bên trái nhấp vào Quota Management, rồi mở rộng phần Create Quota Template, sao đó nhấp vào Create Quota Template… trên bảng điều khiển bên phải như được hiển thị trong ảnh chụp màn hình bên dưới.
![image](https://user-images.githubusercontent.com/101684058/163305708-44c0470b-9dad-4bb8-a896-54da1a4a42c7.png)

Bước 3 - Một bảng mới sẽ được mở ra, trong đó khía cạnh quan trọng nhất cần đặt là Space Limit, tùy theo nhu cầu của bạn. Ở đây, ví dụ này sẽ đặt 2GB và sau đó bấm OK.

![image](https://user-images.githubusercontent.com/101684058/163306356-a2f0acf3-2070-45cc-856c-c11a6f866600.png)

Bước 4 - Bạn phải đặt một định mức định cho nó và một khi thư mục đạt đến định mức đó, nó sẽ gửi cho bạn một thông báo về nơi bạn sẽ có tùy chọn để đặt email.

![image](https://user-images.githubusercontent.com/101684058/163306964-090fc758-8656-41db-999f-200b0426814b.png)

Bước 5 - Nhấp vào Ok.

![image](https://user-images.githubusercontent.com/101684058/163307118-8dee9791-0ecb-4242-9835-deaa2df86325.png)

Bước 6 - Sau đó, để đính kèm định mức này vào một thư mục, nhấp chuột phải vào template rồi kích vào Create Quota from Template…

![image](https://user-images.githubusercontent.com/101684058/163307939-5eada691-9d1a-4c39-acf2-a3b520f528d2.png)

Bước 7 - Nhấn vào Browse… và sau đó chọn thư mục của bạn. Bấm Create.

![image](https://user-images.githubusercontent.com/101684058/163308043-c9a8ad7f-dfdd-411f-afec-661c911082e5.png)

Bước 8 - Để đặt hạn chế cho các thư mục của bạn, bạn có thể chuyển đến cửa sổ bên trái File Screening Management > File screening templates, rồi nhấp vào bảng điều khiển bên trái Create File Screen Template…

![image](https://user-images.githubusercontent.com/101684058/163308741-50d83293-eedd-4a1a-987d-681e830784a8.png)

Bước 9 - Nhấp vào Browse… và tìm thư mục bạn muốn chọn. Cuối cùng hãy bấm Create.

![image](https://user-images.githubusercontent.com/101684058/163309067-81757638-bf3a-44f0-990c-c9846f5bde99.png)


## Hướng dẫn cài đặt plugin giúp điện thoại và máy tính chơi chung với nhau.
- Mình sẽ hướng dẫn các bạn cài đặt plugin giúp các bạn chơi Minecraft trên điện thoại có thể kết nối, chơi chung với các bạn chơi Minecraft trên máy tính.
- Để làm được điều này, ta cần tới plugin có tên là **Geyser**, cách cài đặt rất đơn giản.
- Đầu tiên bạn truy cập link sau đây:
https://geysermc.org/
![image](https://github.com/onionchibi/minecraft-server-guide/assets/86107757/3d60ac21-4336-4abd-a074-dd86a24f3ca3)

Các bạn tải 2 file như trên hình: **Geyser** và **Floodgate**.
Cho dễ hiểu, **floodgate** chính là `online-mode=false` cho điện thoại.
- Sau khi tải về, các bạn copy cả 2 file vào thư mục `plugins` trong thư mục server gốc của các bạn (Hãy chắc chắn rằng server của bạn đã stop). Sau đó tiến hành khởi động lại server.
- Sau khi server khởi động xong, gõ **stop** để tắt server.
- Mở thư mục `plugins`, tại đây bạn sẽ thấy 2 thư mục mới đó là: `Geyser-Spigot` và `floodgate`.
- Trong thư mục `Geyser-Spigot`, mở file `config.yml` bằng **Notepad++**.
- Tìm **auth-type:**, chỉnh `online` thành `floodgate` và lưu lại.

IP kết nối: **Public IPv4**, port mặc định.

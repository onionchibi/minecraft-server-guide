### Hướng dẫn host server Minecraft trực tiếp trên máy tính chi tiết nhất có thể.
Trong bài viết này mình sẽ hướng dẫn các bạn host một server Minecraft trực tiếp trên máy tính của các bạn, sử dụng Spigot.
**_Spigot là server mặc định, không tuỳ biến, tinh chỉnh bất cứ thứ gì, nên so với paper hay purpur thì hiệu suất sẽ kém hơn, nhưng bù lại vì nó là server gốc chuẩn nên hầu như không có lỗi xảy ra._**

_(Paper, Purpur…làm tương tự)._

Chú ý: tất cả kiến thức dưới đây là kinh nghiệm của cá nhân mình, nên có thể sẽ có sai sót, nếu có ý kiến đóng góp, vui lòng liên hệ với mình để mình hoàn thiện hướng dẫn này hơn, xin cảm ơn.

**Thông tin liên hệ vui lòng xem cuối bài viết.**

Đầu tiên để host được server Minecraft trên máy tính, cấu hình máy tính của bạn cần tối thiểu như sau:
- CPU: tối thiểu 2 nhân trở lên.
- Ram: tối thiểu 8GB trở lên.

### Công cụ, phần mềm cần thiết:
- Java JDK **(x64 Installer hoặc X64 MSI Installer)**: [https://www.oracle.com/java/technologies/downloads/#java20](url)
- Notepad++: [https://notepad-plus-plus.org/downloads/](url)

### Mở port:
_Hiểu đơn giản, port giống như cánh cổng có quyền cho vào hay không với các dữ liệu muốn ra vào hệ thống máy tính của bạn. Nếu bạn không mở port, người khác sẽ không thể tham gia vào máy chủ của bạn._
- Port mặc định của Minecraft: **25565**

Vì mở port yêu cầu cần truy cập vào modem, và có rất nhiều loại modem + nhà mạng khác nhau nên mình sẽ không hướng dẫn cụ thể ở đây, các bạn có thể tham khảo trên các trang mạng hướng dẫn đúng với modem và nhà mạng đang dùng, nếu bạn không biết cách mở, vui lòng liên hệ với mình.

Hiện đuôi file, xem phần mở rộng file: [https://quantrimang.com/cong-nghe/cach-hien-duoi-file-tren-windows-179704](url)

### Xây dựng/tải file server:
**(*)** Tải về file server Paper, Purpur...(Nếu sử dụng Spigot, vui lòng bỏ qua bước này):

- Paper: [https://papermc.io/downloads/paper](url)
- Purpur: [https://purpurmc.org/downloads](url)
- Pufferfish: [https://pufferfish.host/downloads](url)

Xây dựng Spigot: (Nếu sử dụng Paper, Purpur hoặc server khác, vui lòng bỏ qua bước này):

- Tải **BuildTools** để xây dựng Spigot: [BuildTools.jar](https://hub.spigotmc.org/jenkins/job/BuildTools/lastSuccessfulBuild/artifact/target/BuildTools.jar)

- Copy **BuildTools.jar** vào một thư mục mới ngoài desktop để dễ làm việc.

- Cũng trong thư mục trên, tạo một file **Text Document** với tên bất kỳ với đuôi mở rộng là **.bat**, ví dụ _**Run.bat**_.

Ấn chuột phải vào file **Run.bat**, chọn _Edit with Notepad++_, sao chép và dán đoạn code dưới đây vào rồi lưu lại:

`java -jar BuildTools.jar --rev latest`

Mặc định **BuildTools** sẽ tạo Spigot phiên bản ổn định mới nhất.

Nếu muốn tạo phiên bản cũ, thay `latest` bằng số phiên bản tương ứng. Ví dụ: `1.19.4`, `1.19.2`...

- Nhấp đúp file **Run.bat** để bắt đầu quá trình xây dựng Spigot, Vui lòng chờ đợi.
- Sau khi hoàn thành, bên trong thư mục sẽ xuất hiện một file **Spigot-x.x.xjar** với `x.x.x` là số phiên bản mà bạn đã xây dựng.

### Chuẩn bị server:

- Copy file server đã xây dựng hoặc tải **(*)** vào một thư mục mới ngoài desktop.
- Trong thư mục trên, tạo một file **Text Document** với tên bất kỳ với đuôi mở rộng là **.bat**, ví dụ _**Start.bat**_.

> (File Start.bat này là file khởi động server).

- Ấn chuột phải vào file **Start.bat**, chọn _Edit with Notepad++_, sao chép và dán đoạn code dưới đây vào rồi lưu lại:
 `java -Xms2G -Xmx2G -XX:+UseG1GC -jar xxx.jar nogui`

`XmsXG`: với `X` là dung lượng ram tối thiểu bạn muốn cho server.

`XmxYG`: với `Y` là dung lượng ram tối đa bạn muốn cho server.

`xxx.jar`: là tên file server của bạn.

- Tiếp tục tạo một file **Text Document** với tên bắt buộc là **eula.txt**.
Nhấn đúp để mở file **eula.txt**, sao chép và dán đoạn code dưới đây vào rồi lưu lại:
`eula=true`

> (EULA là End User License Agreement, có nghĩa Thỏa thuận Giấy phép người dùng cuối, Thỏa thuận sử dụng sản phẩm, Điều kiện sử dụng, Điều khoản Cấp phép Phần mềm)

![image](https://github.com/onionchibi/minecraft-server-guild/assets/86107757/3f46d5d3-619b-42b8-9a99-195967aef1be)


- Nhấp đúp file **Start.bat** để bắt đầu quá trình khởi động server. Vui lòng chờ đợi,
- Server hoàn thành khởi động sẽ có dòng chữ:
`Done (xxxS)! For help, type "help"`
- Gõ **stop** để tắt server.

> (Chú ý, tuyệt đối không tắt server bằng cách ấn X vào góc trên bên phải bảng console, hãy dùng lệnh stop và đợi cho server đóng hoàn toàn).

### Chỉnh sửa server:
- Có 2 giá trị cần nhớ:
`true` = đúng
`false` = sai

**_level-seed=_**: seed của thế giới, nếu bạn muốn tạo thế giới bằng seed, hãy nhập seed vào đây, nếu đã có thế giới cũ trước đó, bạn hãy xoá 3 thư mục: `world`, `world_nether`, `world_the_end` và khởi động lại server để tạo thế giới mới theo seed bạn đã cài đặt.

**_gamemode=_**: chế độ game: `survival` (sinh tồn), `creative` (sáng tạo), `adventure` (phiêu lưu), `spectator` (theo dõi).

**_motd=_**: tên server của bạn, sẽ hiển thị khi người chơi thêm server của bạn vào danh sách server của họ.

**_pvp=_**: cho phép đánh nhau.

**_generate-structures=_**: kiến tạo các kiến trúc trong thế giới (làng…).

**_difficulty=_**: độ khó. `peaceful` (bình yên), `easy` (dễ), `medium` (trung bình), `hard` (khó).

**_max-players=_**: cài đặt giới hạn số người có thể tham gia máy chủ.

**_online-mode=_**: `true`: chỉ có người chơi minecraft bản quyền mới có thể tham gia máy chủ của bạn.

**_sync-chunk-writes=_**: chỉnh `true` thành `false`.

**_hardcore=_**: chế độ chơi siêu khó, chết không hồi sinh.

**_level-type=_**:
     `minecraft\:normal`: là loại thế giới mặc định.
      `flat`: thế giới siêu phẳng.

### **Kết nối server:**

- Bạn có thể kết nối tới server của chính mình bằng IP: `localhost`
- Các bạn cần Public IP để người khác có thể kết nối tới server của bạn:

Vào link sau: https://www.whatismyip.com/
**My Public IPv4** chính là IP để cho người khác có thể tham gia vào máy chủ của bạn.

- Lưu ý: Mỗi lần bạn rút điện modem, Public IPv4 sẽ bị thay đổi.

### Trên đây là tất cả hướng dẫn cơ bản nhất để tạo một server Minecraft trực tiếp trên máy tính của bạn.


Nếu có thắc mắc hoặc cần giúp đỡ, vui lòng liên hệ mình theo Discord: **demoncard09**

Hoặc nhắn tin qua Facebook: [https://www.facebook.com/truonglinhhanh](url)

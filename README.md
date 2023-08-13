### Hướng dẫn host server Minecraft trực tiếp trên máy tính chi tiết nhất có thể.
Trong bài viết này mình sẽ hướng dẫn các bạn host server Minecraft trực tiếp trên máy tính của các bạn.

**Chú ý: tất cả kiến thức dưới đây là kinh nghiệm của cá nhân mình, nên có thể sẽ có sai sót, nếu có ý kiến đóng góp, vui lòng liên hệ với mình để mình hoàn thiện hướng dẫn này hơn, xin cảm ơn.**

**Thông tin liên hệ vui lòng xem cuối bài viết.**

Đầu tiên để host được server Minecraft trên máy tính, cấu hình máy tính của bạn cần tối thiểu như sau:
- CPU: tối thiểu 2 nhân trở lên.
- Ram: tối thiểu 8GB trở lên.

### Công cụ, phần mềm cần thiết:
- Java JDK **(x64 Installer hoặc X64 MSI Installer)**: https://www.oracle.com/java/technologies/downloads/#java20
- Notepad++: https://notepad-plus-plus.org/

### Mở port:
_Hiểu đơn giản, port giống như cánh cổng có quyền cho vào hay không với các dữ liệu muốn ra vào hệ thống máy tính của bạn. Nếu bạn không mở port, người khác sẽ không thể tham gia vào máy chủ của bạn._
- Port mặc định của Minecraft: **25565**

Vì mở port yêu cầu cần truy cập vào modem, và có rất nhiều loại modem + nhà mạng khác nhau nên mình sẽ không hướng dẫn cụ thể ở đây, các bạn có thể tham khảo trên các trang mạng hướng dẫn đúng với modem và nhà mạng đang dùng, nếu bạn không biết cách mở, vui lòng liên hệ với mình.

Hiện đuôi file, xem phần mở rộng file: https://quantrimang.com/cong-nghe/cach-hien-duoi-file-tren-windows-179704

### Xây dựng/tải file server:
**(*)** Tải về file server Paper, Purpur...(Nếu sử dụng Spigot, vui lòng bỏ qua bước này):

- Paper: https://papermc.io/
- Purpur: https://purpurmc.org/
- Pufferfish: https://pufferfish.host/

Xây dựng Spigot: (Nếu sử dụng Paper, Purpur hoặc server khác, vui lòng bỏ qua bước này):

- Tải **BuildTools** để xây dựng Spigot: https://hub.spigotmc.org/jenkins/job/BuildTools/

- Copy **BuildTools.jar** vừa tải vào một thư mục mới ngoài desktop để dễ làm việc.

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

### Cách mở server bẳng Docker (Tạo server nâng cao)

## Bước 1: Cài Docker
- Đối với MacOS / Window: https://www.docker.com
- Đối với Linux:
```
Arch:
1. sudo pacman -S docker
2. sudo systemctl start docker.service
3. sudo systemctl enable docker.service
4. sudo usermod -aG docker $USER
```

```Debian
1. sudo apt install docker.io -y
```

```Ubuntu
1. sudo snap install docker / sudo apt install docker.io -y
```

## Bước 2: Setup 
- Khi cài xong docker thì hãy tạo file tên .env và paste code này vào đó
```env
CONTAINER_NAME=
RAM_AMOUNT=
```
- Khi cài xong docker thì hãy tạo file tên docker-compose.yml và paste code này vào đó
```docker-compose.yml
version: "3"

services: 
    minecraft-server:
        build:
            context: .
            args:
                RAM_AMOUNT: ${RAM_AMOUNT}
        volumes:
            - .server-data:/server
        ports:
            - 25565:25565
        container_name: ${CONTAINER_NAME}

volumes:
    server-data:
```

- Sau khi tạo file docker-compose.yml thì hãy tạo file Dockerfile và paste dòng code này
```Dockerfile
FROM openjdk:16-jdk-alpine

ARG RAM_AMOUNT

ENV ram=${RAM_AMOUNT}

WORKDIR /server

CMD echo "Server Startịng \n" && java -Xms${ram} -Xmx${ram} --add-modules=jdk.incubator.vector -jar paper-1.16.5-794.jar
```

- Sau khi hoàn thành bạn hãy kéo lên trên để xem hướng dẫn nhé

### Lưu ý: 
## Trong file .env CONTAINER_NAME bạn có thể nhập bừa vì nó không ảnh hưởng gì mấy
## Trong file .env RAM_AMOUNT chỉ cho sễ RAM bạn dùng để mở server (Ví dụ: Cấu hình máy là 64GB RAM bạn muốn mở 32GB RAM thì ghi 32768M / 32G / 32000M
## Trong file docker-compose.yml nếu server bạn mở thêm cho người dùng BE (Bugrock Edition) thì hãy thêm vào mục ports
```
- 19132:19132
```
## Trong file Dockerfile openjdk:16-jdk-alpine để chỉ cho phiên bản java bạn dùng để mở server. Nếu phiên bản của bạn yêu cầu java 17 đổ lên thì đởi thành openjdk:17-jdk-alpine
## Trong file Dockerfile paper-1.16.5-794.jar để chỉ cho file server, bạn sẽ phải đổi đúng với file bạn tải
## Nếu bạn chọn dùng docker thì bạn sẽ không càn phải cài java nhé 
## 2023 rồi đừng Spigot hay Bukkit nữa. Paper / Folia / Purpur đi


### Tags
## Ngoài ra còn có các loại Tags bạn có thể dùng (tham khảo tại [ĐÂY](https://flags.sh) )
```-XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=200 -XX:+UnlockExperimentalVMOptions -XX:+DisableExplicitGC -XX:+AlwaysPreTouch -XX:G1HeapWastePercent=5 -XX:G1MixedGCCountTarget=4 -XX:InitiatingHeapOccupancyPercent=15 -XX:G1MixedGCLiveThresholdPercent=90 -XX:G1RSetUpdatingPauseTimePercent=5 -XX:SurvivorRatio=32 -XX:+PerfDisableSharedMem -XX:MaxTenuringThreshold=1 -Dusing.aikars.flags=https://mcflags.emc.gs -Daikars.new.flags=true -XX:G1NewSizePercent=30 -XX:G1MaxNewSizePercent=40 -XX:G1HeapRegionSize=8M -XX:G1ReservePercent=20 ```


### Trên đây là tất cả hướng dẫn cơ bản nhất để tạo một server Minecraft trực tiếp trên máy tính của bạn.


Nếu có thắc mắc hoặc cần giúp đỡ, vui lòng liên hệ mình theo Discord: **demoncard09** và **_itzdenki** (nếu bạn muốn mở như docker)

Hoặc nhắn tin qua Facebook: https://www.facebook.com/truonglinhhanh/

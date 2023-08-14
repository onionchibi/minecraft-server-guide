## 🐳 Cách mở server bẳng Docker (Herta-Chan)

### Bước 1: Cài Docker
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

### Bước 2: Setup 
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

## ⚠️ Lưu ý: 
### Trong file .env CONTAINER_NAME bạn có thể nhập bừa vì nó không ảnh hưởng gì mấy
### Trong file .env RAM_AMOUNT chỉ cho số RAM bạn dùng để mở server (Ví dụ: Cấu hình máy là 64GB RAM bạn muốn mở 32GB RAM thì ghi 32768M / 32G / 32000M
### Trong file docker-compose.yml nếu server bạn mở thêm cho người dùng BE (Bugrock Edition) thì hãy thêm vào mục ports
```
- 19132:19132
```
### Trong file Dockerfile openjdk:16-jdk-alpine để chỉ cho phiên bản java bạn dùng để mở server. Nếu phiên bản của bạn yêu cầu java 17 đổ lên thì đởi thành openjdk:17-jdk-alpine
### Trong file Dockerfile paper-1.16.5-794.jar để chỉ cho file server, bạn sẽ phải đổi đúng với file bạn tải


## 🏷️Tags
### Ngoài ra còn có các loại Tags bạn có thể dùng (tham khảo tại [ĐÂY](https://flags.sh) )
```-XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=200 -XX:+UnlockExperimentalVMOptions -XX:+DisableExplicitGC -XX:+AlwaysPreTouch -XX:G1HeapWastePercent=5 -XX:G1MixedGCCountTarget=4 -XX:InitiatingHeapOccupancyPercent=15 -XX:G1MixedGCLiveThresholdPercent=90 -XX:G1RSetUpdatingPauseTimePercent=5 -XX:SurvivorRatio=32 -XX:+PerfDisableSharedMem -XX:MaxTenuringThreshold=1 -Dusing.aikars.flags=https://mcflags.emc.gs -Daikars.new.flags=true -XX:G1NewSizePercent=30 -XX:G1MaxNewSizePercent=40 -XX:G1HeapRegionSize=8M -XX:G1ReservePercent=20 ```

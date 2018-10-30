# Hướng dẫn cấu hình GitTea + Drone
1. Khởi động docker-compose
```
git clone https://github.com/TechMaster/giteadrone.git
cd giteadrone
docker-compose up -d
```
2. Mở browser vào xem Gitea http://YourComputerIPAddressNotLocalHost:3000
3. Tạo một user đầu tiên. User này sẽ là Administrator của Gitea
4. Để không cho public user tùy tiện đăng ký thì sau khi Admin user đăng ký thành công thì vào
file /data/gitea/conf/app.ini 
DISABLE_REGISTRATION = true
5. Để quản lý Drone CI vào http://YourComputerIPAddressNotLocalHost:8381

# Một số điểm cần lưu ý
1. gitea-server nạp cấu hình gitea-app.ini vào data/gitea/conf/app.ini
2. Hãy generate security key ở mục [security] trong gitea-app.ini
```ini
[security]
INSTALL_LOCK   = true
SECRET_KEY     = ZkHimzDNSjxxgAPAR3lfAjHMjpE8XbNLG0okMDQ7O1SIoZTZJ91Bca7RvL4KDSJ
INTERNAL_TOKEN = eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NDA4MDI2Nzh9.6
```
3. Drone CI không thể kết nối vào Postgresql. Do đó tạm thời để nó ghi vào SQLite3
4. Hãy chỉnh mục [database] trong file app.ini để phù hợp cấu hình user, pass của db
```ini
[database]
DB_TYPE  = postgres
HOST     = db:5432
NAME     = gitea
USER     = gitea
PASSWD   = HayChoToiHaiDiemTua-
```



# Tại sao dùng Gitea + Drone thay cho Gitlab CI?
1. Gitlab chạy chậm tốn tài nguyên
2. Gitlab CI chạy cũng chậm nốt. Bạn có biết Gitlab viết bằng Ruby On Rails không?





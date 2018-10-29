# Hướng dẫn cấu hình GitTea + Drone
```
docker-compose up -d
```

Sau đó mở trình duyệt vào http://localhost:3000


# Giải thích
Tại sao dùng Gitea + Drone thay cho Gitlab CI
1. Gitlab chạy chậm tốn tài nguyên
2. Gitlab CI chạy cũng chậm nốt

Bạn có biết Gitlab viết bằng Ruby On Rails không?


gitea-app.ini sẽ được map volume vào thư mục data/gitea/conf

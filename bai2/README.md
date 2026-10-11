# Bài 2: Khởi chạy Web Server Nginx với Port Mapping

## 1. Mục tiêu
- Khởi chạy Nginx container bằng Docker.
- Ánh xạ cổng máy tính 8080 tới cổng container 80.
- Kiểm tra phản hồi HTTP bằng curl.
- Dừng và xóa container sau khi thử nghiệm.

## 2. Khởi chạy container

```bash
docker run -d -p 8080:80 --name my-web nginx:alpine
```

## 3. Kiểm tra container

```bash
docker ps
```

Container `my-web` hoạt động với port mapping `8080:80`.

## 4. Kiểm tra Web Server

```bash
curl http://localhost:8080
```

Kết quả: Nginx trả về HTML của trang mặc định, chứa nội dung `Welcome to nginx!`.

## 5. Dọn dẹp container

```bash
docker stop my-web
docker rm my-web
docker ps -a
```

Container đã được dừng và xóa sau khi kiểm tra.

## 6. Kết quả
- Khởi chạy thành công Nginx sử dụng image `nginx:alpine`.
- Truy cập Web Server qua cổng 8080.
- Xác nhận phản hồi HTML bằng curl.
- Hoàn thành việc dọn dẹp container.
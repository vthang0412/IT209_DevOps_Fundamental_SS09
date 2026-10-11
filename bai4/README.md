# Bài 4: Lưu trữ dữ liệu với Docker Volume

## 1. Mục tiêu
Tạo Named Volume để lưu trữ dữ liệu bền vững giữa các lần chạy Container.

## 2. Các lệnh thực hiện

**Tạo Volume:**
```bash
docker volume create easy-volume
```

**Ghi dữ liệu vào Volume:**
```bash
docker run --rm -v easy-volume:/data alpine sh -c "echo 'Luu tru du lieu Docker' > /data/test.txt"
```

**Đọc dữ liệu bằng container thứ hai:**
```bash
docker run --rm -v easy-volume:/data alpine cat /data/test.txt
```

**Kiểm tra danh sách Volume:**
```bash
docker volume ls
```

**Kiểm tra dữ liệu lần nữa:**
```bash
docker run --rm -v easy-volume:/data alpine cat /data/test.txt
```

## 3. Kết quả
- Volume `easy-volume` được tạo thành công.
- Dữ liệu được ghi vào `/data/test.txt`.
- Container thứ hai đọc lại được dữ liệu.
- Dữ liệu vẫn tồn tại sau khi container kết thúc.

**Kết luận:** Docker Volume giúp lưu trữ dữ liệu độc lập với vòng đời của Container.
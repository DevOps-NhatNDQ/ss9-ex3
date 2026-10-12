# Báo cáo: Đóng gói trang Web HTML tĩnh với Dockerfile

## 1. Cấu trúc thư mục
```text
.
├── Dockerfile
├── index.html
└── README.md

```

## 2. Quá trình thực hiện

* Tạo nội dung HTML: Ghi chuỗi `<h1>Hello Docker Session 09!</h1>` vào `index.html`.
* Viết Dockerfile: Kế thừa `nginx:alpine` và sao chép `index.html` vào đường dẫn `/usr/share/nginx/html/index.html`.

## 3. Các lệnh thực thi và kiểm tra

```bash
# Build image
docker build -t my-html-app:v1 .

# Khởi chạy container
docker run -d -p 8081:80 --name html-app my-html-app:v1

# Kiểm tra phản hồi HTTP
curl http://localhost:8081

```

## 4. Kết quả kiểm tra

```html
<h1>Hello Docker Session 09!</h1>

```

## 5. Dọn dẹp (tùy chọn)

```bash
docker stop html-app && docker rm html-app

```

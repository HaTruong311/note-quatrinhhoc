# Docker
### Docker là gì:
Docker là nền tảng cung cấp môi trường tiêu chuẩn để chạy app.

Docker đóng gói phần mềm thành các container,Khi cần deploy app lên server, chỉ cần run container của Docker thì app sẽ được khởi chạy ngay lập tức
### Quy trính hoạt động:
1 Viết Dockerfile: Mô tả cách tạo image (cài đặt OS, môi trường, code, lệnh khởi động).

2 Build Image: Dùng docker build để tạo image từ Dockerfile.

3 Run Container: Dùng docker run để tạo container từ image.

4 Container hoạt động như một ứng dụng độc lập, dùng tài nguyên từ hệ thống chủ nhưng tách biệt.
### Các khải niệm cơ bản:
* **Dockerfile**: là file config cho Docker để build ra image. Dockerfile mô tả các bước để hướng dẫn docker build docker image. Nó định nghĩa từng bước để ứng dụng bạn có thể chạy được trong container.
* **image**: docker image như 1 môi trường chuẩn chứa tất cả các thành phần cần thiết để chạy ứng dụng. Là một tập hợp các file hệ thống và file thực thi được gói gọn lại để có thể chạy trong môi trường cô lập của Docker
* **Container**: là một hộp chứa ứng dụng + toàn bộ những gì ứng dụng cần để chạy, như: mã nguồn, thư viện, cấu hình, hệ điều hành tối thiểu. Container hoạt động như một ứng dụng độc lập, dùng tài nguyên từ hệ thống chủ nhưng tách biệt
* **Kết luận**: dockerfile hướng dẫn cho docker build docker image và docker image là môi trường tiêu chuẩn để app chạy và container là hộp chứa ứng dụng đang chạy từ một image. (khi chạy image thì nó chính là container).
### Dockerfile
Các config của Dockerfile:

1. Lệnh nền tảng (Base Image):
* FROM — Chỉ định image cơ sở để xây dựng container

2. Thư mục làm việc và copy file:
* WORKDIR — TThiết lập thư mục làm việc bên trong container
* COPY — Copy file/folder từ máy mình vào trong container.
* ADD — Giống COPY nhưng hỗ trợ thêm:.giải nén(.tar) và tải file từ URL 

3. Cài đặt phần mềm và môi trường:
* RUN — Chạy lệnh trong quá trình build image (Thường dùng để cài đặt phần mềm, cập nhật hệ thống, tạo file...).
* ENV — Thiết lập biến môi trường trong container.

4. Mở cổng và volume:
* EXPOSE — Thông báo port mà container dùng (chỉ mang tính mô tả, không tự động mở).
* VOLUME — Định nghĩa volume bên trong container (thường để chứa dữ liệu cần lưu trữ).

5. Lệnh khởi chạy khi container chạy:
* CMD — Lệnh chính chạy khi container khởi động. Có thể override bằng lệnh ```docker run```.
* ENTRYPOINT — Giống CMD nhưng không thể bị override hoàn toàn, chỉ nhận thêm tham số.

6. Tối ưu nâng cao (tùy chọn):
* LABEL — cung cấp metadata cho image. Có thể sử dụng để add * thông tin maintainer. Để xem các label của images, dùng lệnh docker inspect.
* ARG — Định nghĩa giá trị biến được dùng trong lúc build image(khác ENV là không tồn tại trong container).

# luồng hoạt động web app
1 Người dùng gửi yêu cầu: bằng cách tương tác trực tiếp với giao diện web => trình duyệt sẽ gửi yêu cầu đến web server.

2 Web server nhận yêu cầu phân tích URL và chuyển yêu cầu đến phần xử lý ứng dụng (Backend).

3 Backend xử lý logic: truy vấn xử lí dữ liệu sau đó tạo kết quả 

4 Web server trả kết quả về cho trình duyệt.

5 Trình duyệt hiển thị nội dung cho người dùng.


---
title : "Các mô hình dữ liệu kết nối ứng dụng AWS Amplify và React đầu tiên của bạn với các thành phần giao diện người dùng"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
Trong bài học này, chúng ta sẽ liên kết dữ liệu do AWS Amplify tạo với Thành phần giao diện người dùng. 

### Hướng dẫn

1. Chuyển đến **Thư viện giao diện người dùng** trong Studio. Chọn `NoteUI` sau đó nhập vào **Cấu hình**
![](/images/4-Connect-Data-Models/Connect-Data-Models-1.png?featherlight=false&width=90pc)
2. Nhấp vào tiêu đề trên thẻ hiện có nội dung `T-Shirt`.
![](/images/4-Connect-Data-Models/Connect-Data-Models-2.png?featherlight=false&width=90pc)
Ở phía bên phải của trang, Chọn **Đặt nhãn văn bản**. Chúng tôi sẽ muốn đặt tiêu đề này thành tiêu đề của ghi chú.

- Đặt giá đỡ nhãn: `note.title`. 
![](/images/4-Connect-Data-Models/Connect-Data-Models-9.png?featherlight=false&width=90pc)
Bạn sẽ thấy văn bản áo phông thay đổi thành một trong các tiêu đề của một trong các ghi chú được tạo. Nếu bạn nhấp vào **Xáo trộn dữ liệu xem trước**, bạn sẽ xoay vòng qua các ghi chú khác nhau!
![](/images/4-Connect-Data-Models/Connect-Data-Models-3.png?featherlight=false&width=90pc)
3. Làm tương tự cho văn bản ghi chú - chọn đoạn bên dưới tiêu đề.
- Đặt label thành `note.title`.
- Nhấp vào biểu tượng thùng rác. 
- Đặt `onClick` giá đỡ thành `Delete` dưới dữ liệu. Sau đó chọn `Note` kiểu máy và đặt ID thành `note.id`
![](/images/4-Connect-Data-Models/Connect-Data-Models-4.png?featherlight=false&width=90pc)
#### Tạo biểu mẫu

1. Quay lại **Thư viện giao diện người dùng.**
2. Bấm vào `CreateNote` biểu mẫu, sau đó chọn **Cấu hình**. Nhấp vào **Lưu** và thêm 
![](/images/4-Connect-Data-Models/Connect-Data-Models-5.png?featherlight=false&width=90pc)
- Prop: `onClick. 
- Hành động: `Create new`.
- Mô hình: `Note`. 
- Sau đó, chọn `title` đầu vào để điền vào trường mô hình tiêu đề và tương tự cho văn bản. 
- Tên `TextField` đến từ Figma - bạn có thể đổi tên các thành phần bên trong nó!
![](/images/4-Connect-Data-Models/Connect-Data-Models-6.png?featherlight=false&width=90pc)
#### Cập nhật biểu mẫu

1. Quay lại **Thư viện giao diện người dùng.**
2. Bấm vào **UpdateNote** , sau đó chọn **Cấu hình**. Nhấp vào **Lưu** và thêm như hình dưới đây.
![](/images/4-Connect-Data-Models/Connect-Data-Models-7.png?featherlight=false&width=90pc)
![](/images/4-Connect-Data-Models/Connect-Data-Models-8.png?featherlight=false&width=90pc)
Bây giờ chúng tôi đã liên kết dữ liệu mà chúng tôi đã tạo trong Amplify Studio với các thành phần giao diện người dùng mà chúng tôi đã tạo trong Figma.










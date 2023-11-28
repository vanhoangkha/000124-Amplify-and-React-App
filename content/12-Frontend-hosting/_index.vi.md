---
title : "Dịch vụ lưu trữ Giao diện người dùng ứng dụng AWS Amplify và React đầu tiên của bạn"
date :  "`r Sys.Date()`" 
weight : 12
chapter : false
pre : " <b> 12. </b> "
---

### Hướng dẫn

Trước tiên, hãy tạo kho lưu trữ GitHub cho ứng dụng của bạn.

1. Chuyển đến [trang repo](https://github.com/new) mới và thêm tên. Sau đó nhấp vào **Tạo kho lưu trữ**. 
![](/images/12-Frontend-hosting/Frontend-hosting-0.png?featherlight=false&width=90pc)
2. Đẩy mã của bạn lên GitHub.
```
git add .
git commit -m "Amplify Studio tutorial"
git remote add origin YOUR_REPO_URL
git push -u origin main
```
![](/images/12-Frontend-hosting/Frontend-hosting-11.png?featherlight=false&width=90pc)
3. Chuyển đến **Bảng điều khiển AWS Amplify** . Chọn ứng dụng Khuếch đại mà bạn đang xây dựng, sau đó nhấp vào ứng dụng đó. Chuyển sang **Hosting environmentstab**, chọn **GitHub**, sau đó nhấp vào **Kết nối nhánh**.
![](/images/12-Frontend-hosting/Frontend-hosting-1.png?featherlight=false&width=90pc)
4. Cấp quyền cho GitHub khi bạn được nhắc.
![](/images/12-Frontend-hosting/Frontend-hosting-2.png?featherlight=false&width=90pc)
5. Sau đó trong danh sách thả xuống, hãy chọn kho lưu trữ của bạn. Cũng chọn chi nhánh bạn muốn triển khai. Sau đó, nhấp vào "Tiếp theo"
![](/images/12-Frontend-hosting/Frontend-hosting-3.png?featherlight=false&width=90pc)
6. chọn môi trường phụ trợ "dàn dựng". Nhấn **Tạo vai trò mới**. 
![](/images/12-Frontend-hosting/Frontend-hosting-4.png?featherlight=false&width=90pc)
7. Nhấn tiếp theo từng màn hình. 
![](/images/12-Frontend-hosting/Frontend-hosting-5.png?featherlight=false&width=90pc)
8. Nhấn **Tạo vai trò**
![](/images/12-Frontend-hosting/Frontend-hosting-6.png?featherlight=false&width=90pc)
9. Sau đó quay lại trang Lưu trữ của Amplify và chọn vai trò của bạn Bấm tiếp.
![](/images/12-Frontend-hosting/Frontend-hosting-7.png?featherlight=false&width=90pc)
10. Nhấp vào **Lưu và triển khai**.
![](/images/12-Frontend-hosting/Frontend-hosting-8.png?featherlight=false&width=90pc)
11. Sau một vài phút, bạn sẽ thấy hộp kiểm cho biết ứng dụng của bạn đã được triển khai!
![](/images/12-Frontend-hosting/Frontend-hosting-9.png?featherlight=false&width=90pc)
12.  Bạn có thể nhấp vào URL để xem hoặc chia sẻ ứng dụng của mình.Từ đây, bạn có thể thêm miền tùy chỉnh, thiết lập xem trước yêu cầu kéo và kiểm soát truy cập.
![](/images/12-Frontend-hosting/Frontend-hosting-10.png?featherlight=false&width=90pc)

Giờ đây, cả giao diện người dùng và chương trình phụ trợ ứng dụng của bạn đều được triển khai lên AWS.


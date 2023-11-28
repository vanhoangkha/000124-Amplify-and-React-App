---
title : "Xóa tài nguyên ứng dụng"
date :  "`r Sys.Date()`" 
weight : 13
chapter : false
pre : " <b> 13. </b> "
---

Bây giờ logic phụ trợ của chúng tôi đã hoàn tất và được triển khai, chúng tôi cần thêm dịch vụ lưu trữ giao diện người dùng vào ứng dụng của mình.

### Hướng dẫn

Hướng dẫn
Trước tiên, hãy tạo kho lưu trữ GitHub cho ứng dụng của bạn. [trang định giá](https://aws.amazon.com/amplify/pricing/) .

Hướng dẫn
Bạn có thể xóa tài nguyên Khuếch đại theo hai cách. Đầu tiên là bằng cách chạy `amplify delete`trong thư mục của dự án từ CLI của bạn.

Cách khác là đi tới [**Bảng điều khiển khuếch đại**](https://console.aws.amazon.com/amplify) , chọn ứng dụng của bạn, sau đó trong menu thả xuống **Hành động**, chọn **Xóa ứng dụng**.

![](/images/13-deletion/delete-1.png?featherlight=false&width=90pc)

Xóa ứng dụng Amplify theo bất kỳ cách nào cũng sẽ xóa tài nguyên AWS khỏi tài khoản của bạn.

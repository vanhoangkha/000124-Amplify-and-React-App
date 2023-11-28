---
title : "Thêm xác thực vào ứng dụng của bạn"
date :  "`r Sys.Date()`" 
weight : 9
chapter : false
pre : " <b> 9. </b> "
---
Chúng tôi sẽ thêm xác thực vào ứng dụng của mình để người dùng có thể được tạo, đăng nhập và đăng xuất.

Chúng tôi sẽ thêm cả ủy quyền và xác thực vào ứng dụng này - hãy nhanh chóng xác định cả hai:

**Ủy quyền** - Cho phép người dùng có các hành động khác nhau mà họ có thể thực hiện, ví dụ: chỉ quản trị viên mới có thể cập nhật các bài đăng trên blog hoặc chỉ người tạo dữ liệu mới có thể xem được.

**Xác thực** - Đảm bảo ai đó đúng như họ nói, chẳng hạn như thông qua việc yêu cầu họ nhập mật khẩu.

### Hướng dẫn

1. Nhấp vào **Xác thực** trong **Thiết lập**. Bạn có thể định cấu hình các cơ chế đăng nhập, thuộc tính, bảo vệ bằng mật khẩu khác nhau, v.v. bằng cách sử dụng biểu mẫu được cung cấp. Chọn cấu hình mặc định, sau đó nhấp vào **Triển khai**.
![](/images/9-Add-Authentication/Add-Authentication-1.png?featherlight=false&width=90pc)
Sau khi công việc triển khai của bạn chạy xong, hãy chạy `amplify pull`trong CLI của bạn để đồng bộ hóa các thay đổi với ứng dụng cục bộ của bạn.

2. Trong **App.js**thành phần, chúng tôi sẽ sử dụng With`Authenticator`chức năng để yêu cầu người dùng đăng nhập để xem trang. Nó cũng sẽ triển khai quy trình tạo người dùng.

- Đầu tiên, nhập thành phần:

```
import { withAuthenticator } from '@aws-amplify/ui-react'
```

- Sau đó, trên dòng xuất của bạn, hãy bọc thành phần Ứng dụng trong hàm:
```
export default withAuthenticator(App)
```

Nếu bạn quay lại ứng dụng của mình, bạn sẽ cần phải đăng nhập để xem trang của mình.
![](/images/9-Add-Authentication/Add-Authentication-2.png?featherlight=false&width=90pc)
3. Hãy triển khai nút đăng xuất! Hàm `withAuthenticator`chuyển một signOuthàm (và thông tin của người dùng) đến thành phần mà nó bao bọc dưới dạng chỗ dựa. Hãy phá hủy nó:

`function App ({ signOut }) {`

4. Trong `NavBar`thành phần chạy chức năng khi nhấp vào nút **Đăng xuất**.
```
<NavBar
  marginBottom='20px' width='100%'
  overrides={{
    Button31502513: { onClick: () => setShowCreateModal(true) },
    Button31502517: {
      onClick: async () => {
        signOut()
      }
    }
  }}
/>
```
 
Bây giờ chúng tôi có một luồng xác thực đầy đủ cho ứng dụng của mình.
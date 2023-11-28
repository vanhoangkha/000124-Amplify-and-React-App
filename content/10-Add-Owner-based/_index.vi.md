---
title : "Thêm quy tắc ủy quyền dựa trên chủ sở hữu"
date :  "`r Sys.Date()`" 
weight : 10
chapter : false
pre : " <b> 10. </b> "
---
Trong ứng dụng ghi chú, người dùng chỉ có thể xem và sửa đổi ghi chú của chính họ. Chúng tôi sẽ thêm các quy tắc ủy quyền vào mô hình dữ liệu của mình để dữ liệu được bảo vệ và chỉ chủ sở hữu của dữ liệu mới có thể truy cập được.

### Hướng dẫn

1. Trong AWS Amplify Studio, chuyển đến `data`tab bên dưới **Thiết lập**. Sau đó nhấp vào mô hình **Ghi chú**. Bật **Bật ủy quyền của chủ sở hữu**. Chọn tất cả các hoạt động. Xóa quy tắc đã có.
![](/images/10-Add-Owner-based/Add-Owner-based-1.png?featherlight=false&width=90pc)
Sau đó nhấp **Lưu và triển khai**.
2. Khi các bản cập nhật dữ liệu của bạn được triển khai, hãy chạy `amplify pull`trong CLI của bạn để đồng bộ hóa các thay đổi của bạn cục bộ.
3. Nhập thư viện DataStore:
```
import { DataStore } from 'aws-amplify'
```
4. Trong `NavBar`thành phần, hãy thêm dòng mã sau để xóa dữ liệu cục bộ trước khi đăng xuất.
```
<NavBar
  marginBottom='20px' width='100%'
  overrides={{
    Button31502513: { onClick: () => setShowCreateModal(true) },
    Button31502517: {
      onClick: async () => {
+       await DataStore.clear()
        signOut()
      }
    }
  }}
/>
```
![](/images/10-Add-Owner-based/Add-Owner-based-2.png?featherlight=false&width=90pc)
Bây giờ chúng tôi có các quy tắc ủy quyền trong ứng dụng của mình.
---
title : "Tạo mô hình dữ liệu"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 1. </b> "
---
Trong bài học này, bạn sẽ tạo ứng dụng AWS Amplify Studio khởi động và tạo mô hình dữ liệu.

### Hướng dẫn
Điều đầu tiên chúng ta cần làm cho ứng dụng ghi chú của mình là tạo các mô hình dữ liệu. Chúng tôi sẽ muốn lưu trữ các ghi chú của mình trong cơ sở dữ liệu để người dùng có thể truy cập chúng trên các thiết bị khác nhau.

Nếu bạn chưa có tài khoản AWS, hãy tiếp tục và [tạo một tài khoản](https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/) . Bạn cũng có thể muốn đọc về [giá](https://aws.amazon.com/amplify/pricing/) AWS Amplify và cách đặt [cảnh báo thanh toán](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/monitor_estimated_charges_with_cloudwatch.html) .

1. Truy cập [Bảng điều khiển AWS Amplify](https://console.aws.amazon.com/amplify). 
![](/images/1-Create-a-Data-Model/Create-a-Data-Model-1.png?featherlight=false&width=90pc)
2. Nhấp vào **Bắt đầu** trong **Amplify Studio**.
![](/images/1-Create-a-Data-Model/Create-a-Data-Model-2.png?featherlight=false&width=90pc)
3. Nhập App name: `ghi chú` . Chọn **Xác nhận triển khai**. 
![](/images/1-Create-a-Data-Model/Create-a-Data-Model-3.png?featherlight=false&width=90pc)
4. Khi ứng dụng triển khai chọn *Khởi chạy studio*.
5. Chọn **Dữ liệu** và **Thiết Lập** trên điều hướng bên trái
![](/images/1-Create-a-Data-Model/Create-a-Data-Model-4.png?featherlight=false&width=90pc)
Các mô hình dữ liệu cho phép chúng ta tổ chức và chuẩn hóa dữ liệu - trong JavaScript sẽ rất khó làm việc với một mảng các đối tượng trong đó mỗi đối tượng có các khóa khác nhau. Thay vào đó, chúng tôi muốn chuẩn hóa dữ liệu của mình để mỗi phiên bản có các thuộc tính giống nhau. Chúng tôi cũng muốn các kiểu dữ liệu được chuẩn hóa.
Ví dụ: nếu bạn định tạo mô hình dữ liệu cho các mặt hàng trong một cửa hàng trực tuyến, bạn sẽ có tên mặt hàng và mô tả mà bạn muốn là chuỗi. Bạn cũng sẽ có giá, số float và hình ảnh, đó sẽ là một URL. Chuẩn hóa dữ liệu của bạn theo cách này sẽ giúp bạn tương tác dễ dàng hơn nhiều.

6. Trong Studio, hãy tạo mô hình dữ liệu **Ghi chú** được đặt tên và **thêm hai trường**, **tiêu đề và văn bản**. Giữ nguyên các kiểu dữ liệu `Strings`.
![](/images/1-Create-a-Data-Model/Create-a-Data-Model-5.png?featherlight=false&width=90pc)
7. Khi bạn đã hoàn thành việc này, hãy nhấp vào **Lưu và triển khai** - giản đồ dữ liệu của bạn sẽ được triển khai tới AWS!
![](/images/1-Create-a-Data-Model/Create-a-Data-Model-6.png?featherlight=false&width=90pc)

#### Lưu trữ dữ liệu AWS Amplify
Khi tạo mô hình dữ liệu bằng AWS Amplify Studio, bạn đang sử dụng DataStore. DataStore lưu trữ dữ liệu của bạn cả trực tuyến và ngoại tuyến mà không cần thực hiện thêm bất kỳ thao tác nào. Trong trình duyệt, nó lưu trữ dữ liệu trong IndexedDB tương tự như localStorage. Nó cũng sẽ lưu dữ liệu của bạn vào đám mây bằng cơ sở dữ liệu Amazon DynamoDB.








---
title : "Thêm chủ đề giao diện người dùng vào Dự án của bạn"
date :  "`r Sys.Date()`" 
weight : 11
chapter : false
pre : " <b> 11. </b> "
---

### Hướng dẫn

1. Trước tiên, hãy cài đặt [Plugin AWS Amplify Theme Editor](https://www.figma.com/community/plugin/1040722185526429545/AWS-Amplify-Theme-Editor) . Sau đó, chuyển đến tệp Figma của dự án của bạn.
2. Nhấp vào biểu tượng Figma trong thanh điều hướng, sau đó nhấp vào **plugin**, sau đó nhấp vào **AWS Amplify Theme Editor**.
![](/images/11-Add-UI-Theme/Add-UI-Theme-1.png?featherlight=false&width=90pc)
3. Bạn sẽ thấy một giao diện để thay đổi chủ đề của ứng dụng. Chọn bất kỳ màu nào bạn thích, sau đó cuộn xuống dưới cùng và nhấp vào **Cập nhật chủ đề**
![](/images/11-Add-UI-Theme/Add-UI-Theme-2.png?featherlight=false&width=90pc)
![](/images/11-Add-UI-Theme/Add-UI-Theme-3.png?featherlight=false&width=90pc)
Bạn sẽ thấy tất cả các thành phần của mình trong tab **Thành phần của tôi** cập nhật để phù hợp với chủ đề màu. Bạn cũng có thể làm điều này với khoảng cách, kích thước phông chữ và các thành phần riêng lẻ.
4. Để đồng bộ hóa cục bộ các thay đổi của bạn, hãy chạy `amplify pull`từ dòng lệnh trong dự án của bạn. Chúng ta sẽ cần chuyển chủ đề màu cho <AmplifyProvider>thành phần trong **index.js** tệp.

- Nhập đối tượng chủ đề:
```
import { studioTheme } from './ui-components'
```
- Sau đó, thêm nó làm chỗ dựa cho `AmplifyProvider`:
```
<AmplifyProvider theme={studioTheme}>
```
Bây giờ chủ đề màu của bạn sẽ khớp với chủ đề bạn đã thiết lập trong Figma! Giờ đây, bạn có thể cập nhật các chủ đề và thành phần trong Figma và đồng bộ hóa chúng với ứng dụng cục bộ của mình.
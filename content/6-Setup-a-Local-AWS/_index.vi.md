---
title : "Thiết lập ứng dụng AWS Amplify cục bộ"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 6. </b> "
---
Đã đến lúc phát triển ứng dụng cục bộ bằng mã! Chúng ta sẽ tạo một ứng dụng React và thiết lập AWS Amplify cho dự án.

### Hướng dẫn

#### Tạo một ứng dụng phản ứng

Đầu tiên, tạo một ứng dụng React bằng giao diện dòng lệnh của bạn. Chúng tôi sẽ sử dụng [Tạo ứng dụng React](https://create-react-app.dev/) để tạo ứng dụng React soạn sẵn.

Chạy `npx create-react-app notes`. Sau đó thay đổi vào thư mục đã tạo, `cd notes`.

#### Chạy Amplify Kéo

1. Chúng ta sẽ cài đặt AWS Amplify CLI: `npm install -g @aws-amplify/cli`.
2. Quay lại Amplify Studio và nhấp vào **Hướng dẫn thiết lập cục bộ**. Tại đây, bạn sẽ nhận được một `amplify pull`lệnh cho ứng dụng của mình - ID ứng dụng sẽ dành riêng cho ứng dụng của bạn. Sao chép lệnh này bằng cách nhấp vào nó, sau đó chạy lệnh trong CLI của bạn.
![](/static/images/6-Setup-aLocal-AWS/Setup-aLocal-AWS-1.png?featherlight=false&width=90pc)
3. Màn hình sẽ hiện thỉ hỏi liệu bạn có muốn đăng nhập vào Amplify CLI trong trình duyệt của mình hay không, chọn **Có** và sau đó bạn sẽ được hỏi các câu hỏi về ứng dụng của mình trong CLI.
![](/static/images/6-Setup-aLocal-AWS/Setup-aLocal-AWS-2.png?featherlight=false&width=90pc)
4. Nhấn enter để trả lời từng câu hỏi mặc định.
5. Mở mã ứng dụng trong trình soạn thảo văn bản của bạn. Bạn sẽ nhận thấy rằng một vài thư mục đã tạo trong Amplify Studio.
![](/static/images/6-Setup-aLocal-AWS/Setup-aLocal-AWS-3.png?featherlight=false&width=90pc)

#### Khuếch đại cấu hình

1. Cài đặt các thư viện Amplify và các thành phần React.
`npm i aws-amplify @aws-amplify/ui-react`
2. Sau khi cài xong mở **/src/index.js** tập tin lên và thêm phần sau vào phía trên mã gốc  React.

    ```
    // src/index.js
    import { Amplify } from 'aws-amplify'
    import config from './aws-exports'

    Amplify.configure(config)
    ```
#### Thiết lập giao diện người dùng khuếch đại

Chúng tôi có một số bước thiết lập cần tuân theo để các thành phần hiển thị như mong đợi.

1. Nhập <AmplifyProvider />thành phần và tệp Amplify CSS.

    ```
    // src/index.js
    import { AmplifyProvider } from '@aws-amplify/ui-react'

    import '@aws-amplify/ui-react/styles.css'
    ```

2. Sau đó, đặt thành phần AmplifyProvider làm thành phần cấp cao nhất cho ứng dụng của bạn theo root.renderphương thức đã có:

    ```
    // src/index.js

    root.render(
    +  <AmplifyProvider>
    <App />
    +  </AmplifyProvider>
    )

    ```
    [](/static/images/6-Setup-aLocal-AWS/Setup-aLocal-AWS-4.png?featherlight=false&width=90pc)
3. Cuối cùng, thêm `Inter` tệp phông chữ vào **src/index.**css:

    ```
    /* src/index.css */
    @import url('https://fonts.googleapis.com/css2?family=Inter:slnt,wght@-10..0,100..900&display=swap');
    ```
    ![](/static/images/6-Setup-aLocal-AWS/Setup-aLocal-AWS-5.png?featherlight=false&width=90pc)
Chúng tôi đã thiết lập một ứng dụng React được liên kết với phụ trợ AWS Amplify và định cấu hình các thành phần giao diện người dùng của Amplify.






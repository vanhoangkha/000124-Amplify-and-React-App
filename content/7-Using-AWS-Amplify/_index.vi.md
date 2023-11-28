---
title : "Cách sử dụng các thành phần AWS Amplify Studio cục bộ"
date :  "`r Sys.Date()`" 
weight : 7
chapter : false
pre : " <b> 7. </b> "
---
Hãy hiển thị các thành phần React do Amplify Studio tạo trong ứng dụng của chúng ta.

### Hướng dẫn

1. Chạy máy chủ phát triển ứng dụng Create React thông qua CLI: `npm run start`. Giữ cho ứng dụng này chạy trong nền để bạn có thể xem các thay đổi của ứng dụng trong trình duyệt.
![](/images/7-Using-AWS-Amplify-Studio/Using-AWS-Amplify-Studio-1.png?featherlight=false&width=90pc)
2. Đi tới **/src/App.js** và xóa phần trả lại thay thế bản soạn sẵn bằng Đoạn phản ứng:
```
function App() {
  return (
    <></>
  )
}
```
Bạn cũng có thể xóa các mục nhập hiện có.

3. Thêm **NavBar** thành phần vào ứng dụng.
```
import { NavBar } from './ui-components'
```
4. Sau đó, tạo một phiên bản thành phần trong return
```
function App() {
  return (
    <>
      <NavBar />
    </>
  )
}
```
![](/images/7-Using-AWS-Amplify-Studio/Using-AWS-Amplify-Studio-0.png?featherlight=false&width=90pc)
5. Khi bạn xem NavBar trong trình duyệt, bạn sẽ nhận thấy rằng nó không trải dài trên toàn bộ trang hãy thêm chỗ dựa width=100% vào thành phần:
```
<NavBar width="100%" />
```
6. Bây giờ, hãy kết xuất bộ sưu tập ghi chú bên dưới tiêu đề:

```
import { NavBar,  NoteUICollection} from './ui-components'

function App() {
  return (
    <>
      <NavBar width="100%" />
      <NoteUICollection />
    </>
  )
}
```
![](/images/7-Using-AWS-Amplify-Studio/Using-AWS-Amplify-Studio-2.png?featherlight=false&width=90pc)

7. Bạn sẽ nhận thấy rằng NavBar thực sự gần với các ghi chú, hãy thêm một lề dưới vào.

```
<NavBar width="100%" marginBottom='20px' />
```
![](/images/7-Using-AWS-Amplify-Studio/Using-AWS-Amplify-Studio-5.png?featherlight=false&width=90pc)

8. Thêm vào cuối **index.css** tệp của mình. Điều này sẽ hữu ích để làm cho bố cục của chúng ta trông đẹp hơn nữa!
```
/* Add to the end of /src/index.css */
.modal {
  position: absolute;
  background-color: white;
  margin-left: auto;
  margin-right: auto;
  width: fit-content;
  left: 0;
  right: 0;
  top: 100px;
  border: .5px solid grey;
}

.container {
  margin: 0 auto;
  max-width: 900px;
}
```
![](/images/7-Using-AWS-Amplify-Studio/Using-AWS-Amplify-Studio-6.png?featherlight=false&width=90pc)
9. Bọc **NoteUICollectiondiv** bằng bộ chứa lớp để chúng được hiển thị ở giữa trang:
```
function App() {
  return (
    <>
      <NavBar width="100%" />
      <div className='container'>
        <NoteUICollection />  
      </div>
    </>
  )
}
```
![](/images/7-Using-AWS-Amplify-Studio/Using-AWS-Amplify-Studio-7.png?featherlight=false&width=90pc)
10. Bạn có thể kiểm tra **CreateNote** biểu mẫu (khi nó không bị ẩn) và nó sẽ thêm một ghi chú mới vào giao diện người dùng của bạn!
```
import { CreateNote, NavBar, NoteUICollection, UpdateNote } from './ui-components'

function App() {
  return (
    <>
      <NavBar width="100%" />
      <div className='container'>
        <NoteUICollection />  
      </div>
      <div className='modal' style={{display: 'none'}}>
        <CreateNote />
      </div>
      <div className='modal' style={{display: 'none'}}>
        <UpdateNote />
      </div>
    </>
  )
}
```
Bây giờ chúng ta đã tạo giao diện người dùng cơ bản cho ứng dụng của mình.





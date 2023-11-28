---
title : "Sửa đổi các thành phần do AWS Amplify Studio tạo trong mã"
date :  "`r Sys.Date()`" 
weight : 8
chapter : false
pre : " <b> 8. </b> "
---
AWS Amplify Studio có nhiều chức năng tạo mã giúp tăng tốc thời gian phát triển; tuy nhiên, nó được xây dựng cho các nhà phát triển nên việc có thể ghi đè tất cả mã được tạo là rất quan trọng. Chúng tôi sẽ sử dụng các phần ghi đè để mở rộng chức năng của các thành phần.

### Hướng dẫn

1. Đầu tiên, chúng ta sẽ tạo các trường trạng thái để biết mỗi phương thức có được hiển thị hay không. Chúng tôi cũng sẽ tạo một trường trạng thái để lưu trữ ghi chú nào sẽ được cập nhật.

```
import { useState } from 'react'

function App () {
  const [showCreateModal, setShowCreateModal] = useState(false)
  const [showUpdateModal, setShowUpdateModal] = useState(false)
  const [updateNote, setUpdateNote] = useState()
...
```
2. Mở `/src/ui-components/NavBar.js`tập tin lên. Bạn sẽ nhận thấy một `Button`thành phần con có `getOverrideProps`bên trong nó.
![](/images/8-Modify-AWS-Amplify-Studio/Modify-AWS-Amplify-Studio-1.png?featherlight=false&width=90pc)
Đối số thứ hai `getOverrideProps`là khóa Figma, trong trường hợp này Button31632483là .

3. Bạn có thể chuyển chỗ dựa `overrides`cho các phiên bản thành phần của mình, phiên bản này sẽ chứa một đối tượng. Key sẽ là key của `subcomponent`, value sẽ là thuộc tính mà chúng ta muốn override. Chúng tôi sẽ thêm một `onClick`nút chuyển đổi `showCreateModal`thành true.
```
<NavBar
  marginBottom='20px' width='100%'
  overrides={{
    Button31502513: { onClick: () => setShowCreateModal(true) }
  }}
/>
```

4. Bây giờ, chúng tôi sẽ hiển thị `CreateNote`phương thức một cách có điều kiện để chỉ hiển thị khi `showCreateModal`là true. Chúng tôi cũng sẽ ghi đè` X`biểu tượng để đóng phương thức. Đối với khả năng truy cập, tôi cũng sẽ đặt nó thành một nút.
```
<div className='modal' style={{ display: showCreateModal === false && 'none' }}>
  <CreateNote overrides={{
    MyIcon: {
      as: 'button',
      onClick: () => setShowCreateModal(false)
    }
  }}
  />
</div>
```
![](/images/8-Modify-AWS-Amplify-Studio/Modify-AWS-Amplify-Studio-1.png?featherlight=false&width=90pc)
![](/images/8-Modify-AWS-Amplify-Studio/Modify-AWS-Amplify-Studio-2.png?featherlight=false&width=90pc)
![](/images/8-Modify-AWS-Amplify-Studio/Modify-AWS-Amplify-Studio-3.png?featherlight=false&width=90pc)

5. Nhấp vào nút chỉnh sửa trên ghi chú sẽ hiển thị phương thức cập nhật và cũng đặt phiên bản ghi chú mà chúng tôi muốn cập nhập/
```
<NoteUICollection overrideItems={({ item, idx }) => {
  return {
    overrides: {
      Vector31472464: {
        as: 'button',
        onClick: () => {
          setShowUpdateModal(true)
          setUpdateNote(item)
        }
      }
    }
  }
}}
/>
```
![](/images/8-Modify-AWS-Amplify-Studio/Modify-AWS-Amplify-Studio-4.png?featherlight=false&width=90pc)

6. Thêm một ghi đè để UpdateNoteẩn phương thức cập nhật khi nó đóng và chúng tôi cũng sẽ chuyển phiên bản của ghi chú mà chúng tôi muốn cập nhật.
```
<div className='modal' style={{ display: showUpdateModal === false && 'none' }}>
  <UpdateNote
    note={updateNote} overrides={{
      MyIcon: {
        as: 'button',
        onClick: () => setShowUpdateModal(false)
      }
    }}
  />
</div>
```
![](/images/8-Modify-AWS-Amplify-Studio/Modify-AWS-Amplify-Studio-6.png?featherlight=false&width=90pc)
Bây giờ giao diện người dùng đầy đủ của chúng tôi đang hoạt động như mong đợi.

Bạn có thể sử dụng các phần ghi đè để tùy chỉnh các thành phần giao diện người dùng do AWS Amplify Studio tạo trong mã của riêng bạn.

---
title : "Modify AWS Amplify Studio Generated Components in Code"
date : "`r Sys.Date()`"
weight : 8
chapter : false
pre : " <b> 8. </b> "
---
AWS Amplify Studio has many code generation capabilities that speed up development time; however, it's built for developers so it's important to be able to override all generated code. We will use overrides to extend the functionality of the components.

### Instruct

1. First, we will create state fields to know if each modal is displayed or not. We'll also create a status field to store which notes should be updated.

    ```
    import { useState } from 'react'

    function App() {
      const [showCreateModal, setShowCreateModal] = useState(false)
      const [showUpdateModal, setShowUpdateModal] = useState(false)
      const [updateNote, setUpdateNote] = useState()
    ...
    ```
2. Open the `/src/ui-components/NavBar.js` file. You will notice a `Button` child component with `getOverrideProps` inside it.
![](/images/8-Modify-AWS-Amplify-Studio/Modify-AWS-Amplify-Studio-1.png?featherlight=false&width=90pc)
The second argument `getOverrideProps` is the Figma key, in this case Button31632483 is .

3. You can pass the `overrides` prop to instances of your component, which will contain an object. Key will be the key of `subcomponent`, value will be the property we want to override. We will add an `onClick` button that toggles `showCreateModal` to true.
    ```
    <NavBar
      marginBottom='20px' width='100%'
      overrides={{
        Button31502513: { onClick: () => setShowCreateModal(true) }
      }}
    />
    ```

4. Now we will conditionally expose the `CreateNote` method to show only when `showCreateModal` is true. We will also override the `X` symbol to close the modal. For accessibility, I would also make it a button.
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

5. Clicking the edit button on the note will show the update method and also set the version of the note we want to update/
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

6. Add an override to UpdateNote to hide the update method when it closes and we will also pass the version of the note that we want to update.
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

Now our full UI is working as expected.
You can use overrides to customize user interface elements created by AWS Amplify Studio in your own code.
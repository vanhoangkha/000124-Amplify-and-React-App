---
title : "Using AWS Amplify Studio Components Locally"
date : "`r Sys.Date()`"
weight : 7
chapter : false
pre : " <b> 7. </b> "
---
Let's show the React components created by Amplify Studio in our app.

### Instruct

1. Run the Create React application development server through the CLI: `npm run start`. Keep this app running in the background so you can see its changes in the browser.
![](/images/7-Using-AWS-Amplify-Studio/Using-AWS-Amplify-Studio-1.png?featherlight=false&width=90pc)
2. Go to **/src/App.js** and remove the return replace boilerplate with React Fragment:
    ```
    function App() {
      return (
        <></>
      )
    }
    ```
You can also delete existing entries.

3. Add **NavBar** component to the application.
    ```
    import { NavBar } from './ui-components'
    ```
4. Then create a component instance in return
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

5. When you view the NavBar in the browser you will notice that it doesn't span the entire page add the width=100% prop to the element:
    ```
    <NavBar width="100%" />
    ```
6. Now render the collection of notes below the title:

    ```
    import { NavBar, NoteUICollection} from './ui-components'

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
7. You will notice that the NavBar is really close to the notes, add a bottom margin.
    ```
    <NavBar width="100%" marginBottom='20px' />
    ```
    ![](/images/7-Using-AWS-Amplify-Studio/Using-AWS-Amplify-Studio-5.png?featherlight=false&width=90pc)

8. Add at the end of your **index.css** file. This will be helpful to make our composition look even better!
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
      border: .5px solid gray;
    }

    .container {
      margin: 0 auto;
      max-width: 900px;
    }
    ```
    ![](/images/7-Using-AWS-Amplify-Studio/Using-AWS-Amplify-Studio-6.png?featherlight=false&width=90pc)
9. Wrap **NoteUICollectiondiv** with a class container so that they are displayed in the center of the page:
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
10. You can check the **CreateNote** form (when it's not hidden) and it will add a new note to your UI!
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
We have now created the basic user interface for our application.
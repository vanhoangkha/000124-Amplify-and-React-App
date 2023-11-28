---
title : "Setup a Local AWS Amplify Application"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 6. </b> "
---
It's time to develop apps locally in code! We will create a React application and set up AWS Amplify for the project.

### Instruct

#### Create a React Application

First, create a React app using your command line interface. We will use Create React App (https://create-react-app.dev/) to create a boilerplate React app.

Run `npx create-react-app notes`. Then change to the created directory, `cd notes`.

#### Run Amplify Pull

1. We will install the AWS Amplify CLI: `npm install -g @aws-amplify/cli`.
2. Return to Amplify Studio and click **Local Setup Guide**. Here you will receive an `amplify pull` command for your application - the application ID will be specific to your application. Copy this command by clicking on it, then run the command in your CLI.
![](/images/6-Setup-aLocal-AWS/Setup-aLocal-AWS-1.png?featherlight=false&width=90pc)
3. A screen will appear asking if you want to log in to the Amplify CLI in your browser, select **Yes** and then you will be asked questions about your application in the CLI.
![](/images/6-Setup-aLocal-AWS/Setup-aLocal-AWS-2.png?featherlight=false&width=90pc)
4. Press enter to answer each default question.
5. Open the application code in your text editor. You will notice that a few folders have been created in Amplify Studio.
![](/images/6-Setup-aLocal-AWS/Setup-aLocal-AWS-3.png?featherlight=false&width=90pc)

#### Amplify Configure

1. Install Amplify libraries and React components.
`npm i aws-amplify @aws-amplify/ui-react`
2. Once installed, open **/src/index.js** file and add the following above the React native code.

     ```
     // src/index.js
     import { Amplify } from 'aws-amplify'
     import config from './aws-exports'

     Amplify.configure(config)
     ```
#### Set Up Amplify UI

We have some setup steps to follow in order for the components to render as expected.

1. Import the <AmplifyProvider /> component and the Amplify CSS file.

     ```
     // src/index.js
     import { AmplifyProvider } from '@aws-amplify/ui-react'

     import '@aws-amplify/ui-react/styles.css'
     ```

2. Then set the AmplifyProvider component as the top-level component for your application according to the existing root.render method:
     ```
     // src/index.js

     root.render(
   + <AmplifyProvider>
     <App />
   + </AmplifyProvider>
     )
     ```
     ![](/images/6-Setup-aLocal-AWS/Setup-aLocal-AWS-4.png?featherlight=false&width=90pc)

3. Finally, add the `Inter` font file to **src/index.**css:
     ```
     /* src/index.css */
     @import url('https://fonts.googleapis.com/css2?family=Inter:slnt,wght@-10..0,100..900&display=swap');
     ```
     ![](/images/6-Setup-aLocal-AWS/Setup-aLocal-AWS-5.png?featherlight=false&width=90pc)
We've set up a React app linked to the AWS Amplify backend and configured Amplify's UI components.
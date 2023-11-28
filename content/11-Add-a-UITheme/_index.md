---
title : "Add UI Themes to your Project"
date : "`r Sys.Date()`"
weight : 11
chapter : false
pre : " <b> 11. </b> "
---

### Instruct

1. First, install the [AWS Amplify Theme Editor Plugin](https://www.figma.com/community/plugin/1040722185526429545/AWS-Amplify-Theme-Editor). Then go to your project's Figma file.
2. Click the Figma icon in the navigation bar, then **plugins**, then click **AWS Amplify Theme Editor**.
![](/images/11-Add-UI-Theme/Add-UI-Theme-1.png?featherlight=false&width=90pc)
3. You will see an interface to change the theme of the application. Choose any color you like, then scroll to the bottom and click **Update Theme**
![](/images/11-Add-UI-Theme/Add-UI-Theme-2.png?featherlight=false&width=90pc)
![](/images/11-Add-UI-Theme/Add-UI-Theme-3.png?featherlight=false&width=90pc)
You'll see all your components in the **My Components** tab updated to match the color theme. You can also do this with spacing, font size, and individual elements.
4. To sync your changes locally, run `amplify pull` from the command line in your project. We will need to pass the color theme to the <AmplifyProvider> element in the **index.js** file.

- Enter subject object:
    ```
    import { studioTheme } from './ui-components'
    ```
- Then add it as a prop for `AmplifyProvider`:
    ```
    <AmplifyProvider theme={studioTheme}>
    ```
    Your color theme should now match the one you set up in Figma! You can now update themes and components in Figma and synchronize them with your local application.
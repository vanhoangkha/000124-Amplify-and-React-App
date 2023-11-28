---
title : "Resources Delete "
date : "`r Sys.Date()`"
weight : 13
chapter : false
pre : " <b> 13. </b> "
---

Now that our backend logic is complete and deployed, we need to add a front end hosting service to our application.

### Instruct

Instruct
First, create a GitHub repository for your app. [pricing page](https://aws.amazon.com/amplify/pricing/) .

Instruct
You can delete an Amplifier resource in two ways. The first is by running `amplify delete` in the project's directory from your CLI.

The alternative is to go to [**Amplify Console**](https://console.aws.amazon.com/amplify) , select your app, then in the **Actions** dropdown menu , select **Delete App**.

![](/images/13-deletion/delete-1.png?featherlight=false&width=90pc)

Deleting the Amplify app in any way will remove AWS resources from your account.
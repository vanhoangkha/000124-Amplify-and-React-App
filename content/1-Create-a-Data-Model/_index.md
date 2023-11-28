---
title : "Create data model"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 1. </b> "
---
In this lesson, you will start the AWS Amplify Studio application and create a data model.

### Instruct
The first thing we need to do for our note-taking app is to create data models. We will want to store our notes in a database so that users can access them on different devices.

If you don't have an AWS account, go ahead and [create one](https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/). You also may want to read about AWS Amplify [pricing](https://aws.amazon.com/amplify/pricing/) and how to set a [billing alarm](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/monitor_estimated_charges_with_cloudwatch.html).

1. Go to the [AWS Amplify Console](https://console.aws.amazon.com/amplify).
![](/images/1-Create-a-Data-Model/Create-a-Data-Model-1.png?featherlight=false&width=90pc)
2. Continue to **Start** in **Amplify Studio.**
![](/images/1-Create-a-Data-Model/Create-a-Data-Model-2.png?featherlight=false&width=90pc)
3. Enter Application Name: `notes` . Select **Confirm Development.**
![](/images/1-Create-a-Data-Model/Create-a-Data-Model-3.png?featherlight=false&width=90pc)
4. When development app is selected **Launch studio**.
5. Select **Data** and **Setup** on the left navigation
![](/images/1-Create-a-Data-Model/Create-a-Data-Model-4.png?featherlight=false&width=90pc)
Data models allow us to organize and normalize data - in JavaScript it would be very difficult to do with an array of objects where each object has different keywords. Instead, we want to normalize our data so that each version has the same properties. We also want the data types to be normalized.
For example, if you are going to create a data model for items in an online store, you will have the item name and description you want as strings. You will also have the price, float and image, which will be a URL. Normalizing your data in this way will make your interaction much easier.

6. In Studio, create a named **Notes** data model and **add two fields**, **title and text**. Preserve the `String` data type.
![](/images/1-Create-a-Data-Model/Create-a-Data-Model-5.png?featherlight=false&width=90pc)
7. Once you've done this, click **Save and deploy** - your data will simply be mined to AWS!
![](/images/1-Create-a-Data-Model/Create-a-Data-Model-6.png?featherlight=false&width=90pc)

#### AWS Amplify Data Storage
When you create a data model with AWS Amplify Studio, you are using the DataStore. DataStore stores your data both online and offline without any extra work. In the browser, it stores data in IndexedDB similar to localStorage. It will also save your data to the cloud using an Amazon DynamoDB database.
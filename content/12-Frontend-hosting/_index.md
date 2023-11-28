---
title : "Hosting Your First AWS Amplify and React App UI"
date : "`r Sys.Date()`"
weight : 12
chapter : false
pre : " <b> 12. </b> "
---

### Instruct

First, create a GitHub repository for your app.

1. Go to the new [repo page](https://github.com/new) and add a name. Then click **Create Repository**.
![](/images/12-Frontend-hosting/Frontend-hosting-0.png?featherlight=false&width=90pc)
2. Push your code to GitHub.
        ```

        git add .

        git commit -m "Amplify Studio tutorial"

        git remote add origin YOUR_REPO_URL

        git push -u origin main
        ```
    ![](/images/12-Frontend-hosting/Frontend-hosting-11.png?featherlight=false&width=90pc)
3. Go to **AWS Amplify Console** . Select the Amplifier app you're building, then click it. Switch to **Hosting environmentstab**, select **GitHub**, then click **Connect Branch**.
![](/images/12-Frontend-hosting/Frontend-hosting-1.png?featherlight=false&width=90pc)
4. Give GitHub permission when you are prompted.
![](/images/12-Frontend-hosting/Frontend-hosting-2.png?featherlight=false&width=90pc)
5. Then in the drop-down list select your repository. Also select the branch you want to deploy to. Then click "Next"
![](/images/12-Frontend-hosting/Frontend-hosting-3.png?featherlight=false&width=90pc)
6. select the "staging" backend environment. Click **Create New Role**.
![](/images/12-Frontend-hosting/Frontend-hosting-4.png?featherlight=false&width=90pc)
7. Next tap each screen.
![](/images/12-Frontend-hosting/Frontend-hosting-5.png?featherlight=false&width=90pc)
8. Click **Create Role**
![](/images/12-Frontend-hosting/Frontend-hosting-6.png?featherlight=false&width=90pc)
9. Then return to Amplify's Archive page and select your role Click Next.
![](/images/12-Frontend-hosting/Frontend-hosting-7.png?featherlight=false&width=90pc)
10. Click **Save and Deploy**.
![](/images/12-Frontend-hosting/Frontend-hosting-8.png?featherlight=false&width=90pc)
11. After a few minutes, you should see a checkbox that says your app is deployed!
![](/images/12-Frontend-hosting/Frontend-hosting-9.png?featherlight=false&width=90pc)
12. You can click the URL to view or share your app. From here you can add a custom domain, set up pull request previews, and control access.
![](/images/12-Frontend-hosting/Frontend-hosting-10.png?featherlight=false&width=90pc)

Now, both your application frontend and backend are deployed to AWS.
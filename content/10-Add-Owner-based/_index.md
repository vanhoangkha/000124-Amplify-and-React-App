---
title : "Add owner-based authorization rule"
date : "`r Sys.Date()`"
weight : 10
chapter : false
pre : " <b> 10. </b> "
---
In the notes app, users can only view and modify their own notes. We will add authorization rules to our data model so that the data is protected and can only be accessed by the owner of the data.

### Instruct

1. In AWS Amplify Studio, go to the `data` tab under **Setup**. Then click the **Note** model. Enable **Enable Owner Authorization**. Select all activities. Delete an existing rule.
![](/images/10-Add-Owner-based/Add-Owner-based-1.png?featherlight=false&width=90pc)
Then click **Save and Deploy**.
2. Once your data updates are deployed, run `amplify pull` in your CLI to sync your changes locally.
3. Import the DataStore library:
    ```
    import { DataStore } from 'aws-amplify'
    ```
4. In the `NavBar` component, add the following line of code to clear local data before logging out.
    ```
    <NavBar
      marginBottom='20px' width='100%'
      overrides={{
        Button31502513: { onClick: () => setShowCreateModal(true) },
        Button31502517: {
          onClick: async() => {
    + await DataStore.clear()
            signOut()
          }
        }
      }}
    />
    ```
    ![](/images/10-Add-Owner-based/Add-Owner-based-2.png?featherlight=false&width=90pc)
We now have authorization rules in our application.
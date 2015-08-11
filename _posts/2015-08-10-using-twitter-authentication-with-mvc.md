---
layout: post
title: "Using Twitter Authentication with MVC"
excerpt: "Setting up authentication using Twitter is incredibly simply in MVC5. Here is a quick walk-through of its implementation."
tags: [OAuth, ASP.Net, MVC]
comments: true
---

Setting up an authentication service using Twitter is a breeze in MVC (version 5 in this case). Below is a quick walk-through of how this is done.

**Prequisites**:

* Twitter account
* ASP.NET MVC 5 Project


**Steps**:

1. Create App on Twitter Developers
2. Add Consumer Key and Secret to your MVC app.
3. Use your Twitter Auth

## Create an App on Twitter Developers

Head over to [Twitter Developers](https://dev.twitter.com/) site. Just above the footer, in the **Tools** section, click on '*Manage Your App*'.

![screenshot of Twitter Developers Manage App link]({{ site.url }}/images/manage-app.jpg)

In **Twitter Apps** click '*Create New App*' in the upper right hand corner.

* **Name**: Provide application name
* **Description**: Provide application description
* **Website**: Publicly accessible home page. If you do not have this yet, you can add a placeholder url (i.e. http://localhost)
* **Callback URL**: This value is not required, BUT for MVC, it does actually require a value. As note above, you can put a placeholder value here if you do not have a callback url. In our case, MVC will override whatever value you add in here.

Once you are done adding your Application Details, agree to the terms, then '*Create your Twitter application*"

When the App is created, you will find you *Consumer Key* and *Consumer Secret* in the '*Keys and Access Tokens*' section.

![screenshot of Key and Access Tokens]({{ site.url }}/images/keys-and-access-tokens.jpg)

## Add Consumer Key and Secret to your MVC app
Now that you have your Keys, we can add them into our MVC app. Find and open 'Startup.Auth.cs' in the 'App_Start' directory of your Project.

Uncomment the 'app.UseTwitterAuthentication' section and add in your Keys, then save and build your Project.

![screenshot of adding Twitter Keys]({{ site.url }}/images/startup-auth.jpg)

## Use your Twitter Auth
Navigate to your site and you should now see a Twitter button. Clicking this button will now send a request to Twitter to authenticate a user on your site.

![screenshot of Twitter Auth Button]({{ site.url }}/images/twitter-auth-button.jpg)

### Note on the Twitter App Callback URL setting
`Response status code does not indicate success: 401 (Unauthorized).`

If you do forget to add in a Callback URL, you will most likely receive this error. Just make sure your Callback URL is set in the Twitter App.

![screenshot of Twitter Auth Button]({{ site.url }}/images/twitter-app-error.png)

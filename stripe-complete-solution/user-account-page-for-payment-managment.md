# User account page for payment managment

### **Manage subscriptions page**

You can set up a protected page where subscribers can manage their subscriptions.  
This page lets subscribers update the credit card used for their subscriptions, and also cancel subscriptions.

{% embed url="https://youtu.be/cfr\_MtcP0Zs" %}

{% hint style="info" %}
Use the `[fullstripe_manage_subscriptions]` shortcode on the page where you'd like the "Manage subscription" pane to appear.
{% endhint %}



The user journey is as follows:

1. Subscriber has to enter the email address used for thir subscriptions
2. An email is sent with a security code to the subscriber's email address \(Learn more about setting up your branded email address\)
3. The Subscriber enters security code and is logged in to the "Manage subscription" page

Important: You should protect your subscribers by enabling Google reCaptcha for the "Manage subscription" page.  
  
Follow these steps to turn on Google reCaptcha:

1. Register your site for Google ReCaptcha, and get API keys. 
2. Enable Google reCaptcha on the "Full Stripe -&gt; Settings -&gt; User" page in WP admin, and enter your Google reCaptcha API keys.


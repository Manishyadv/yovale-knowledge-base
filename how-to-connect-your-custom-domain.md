# How to connect your custom domain

Yovale support both naked and subdomain like-

https://yourdomain.com and https://www.yourdomain.com



### **To connect your domain:**

1. Log in to your registrar account

The registrar is where you originally purchased the domain. If you don't remember who your registrar is, you can use [whois.net](http://whois.net/) to find out.

2. Locate the Control Panel or Domain Manager of your domain in your registrar account.

 The control panel allows you to change the DNS records from the default ones provided by the registrar.

Different registrars may have different control panel layouts and other names for it as well. You might find it under 'DNS Manager' or 'Domain Manager".

3. In your registrar's Control Panel, Add a CNAME record-

Type

| Type | Host | Value |
| :--- | :--- | :--- |
| CNAME | @ | `connect.serverlessinfra.com` |

{% hint style="info" %}
If you want to connect a subdomain or a domain with www in front of it, please change the Host value respectively. For example, if you want your domain to be shop.yourdomain.com make sure to use shop in Host value instead of @
{% endhint %}


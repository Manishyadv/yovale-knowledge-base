---
description: Connect your Namecheap domain to your Yovale website.
---

# Namecheap DNS records

  
1. Sign into your **Namecheap account** \(The Sign In option is available in the top hat of the page\).   
  
2. Select **Domain List** from the left sidebar and click on the **Manage** button next to your domain:

domain:  
  
![](https://namecheap.simplekb.com//SiteContents/2-7C22D5236A4543EB827F3BD8936E153E/media/nctutmanage.png)  
  
  
3. Navigate to the **Advanced DNS** tab at the top of the page:   
  
![](https://namecheap.simplekb.com//SiteContents/2-7C22D5236A4543EB827F3BD8936E153E/media/advanced_dns.png)  
  
  
4. Find the **Host records** section and click on the **Add New Record** button.

![](https://namecheap.simplekb.com//SiteContents/2-7C22D5236A4543EB827F3BD8936E153E/media/addnewrecord.png)

5. Choose CNAME Record from drop down options-

![](../.gitbook/assets/screenshot-2018-05-02-20.11.30.png)

6. Enter the required settings and click on ✓ button to save the changes.

  **Host --&gt; WWW                    points to --&gt; yourdomainname.com**

![](../.gitbook/assets/screenshot-2018-05-02-20.12.15.png)

7. Now, add the A record and click on ✓ button to save the changes.

**A record -        Host --&gt; @           points to --&gt; 34.202.63.170**

![](../.gitbook/assets/screenshot-2018-05-02-20.15.31.png)

Thats all your website would be live within few hours. 

**Few important notes:**

1\) It may take up to 24 hours for these changes to propagate worldwide.

2\) If there are previous A records in your DNS settings - make sure to delete them.  



# Settings \(Full Stripe solution\)

This plugin is designed to make it easy for you to accept payments and create subscriptions from your Yovale site. Powered by Stripe, you can embed payment forms into any post or page and take payments directly from your website without making your customers leave for a 3rd party website.



### **Setup**

1. You need a free Stripe account from [Stripe.com](https://stripe.com/)
2. Get your Stripe API keys from your [Stripe Dashboard -&gt; API](https://dashboard.stripe.com/account/apikeys) page
3. Update Full Stripe settings with your API keys and select an API mode. \(Test mode is recommended initially to make sure everything is set up correctly\)
4. Get your plugin's webhook URL on the Full Stripe settings page.
5. Set the webhook URL on the [Stripe Dashboard -&gt; Webhooks -&gt; Settings](https://dashboard.stripe.com/account/webhooks) page. Add endpoints for live and test mode, and make sure that Stripe sends all events \("Send me all events" option\).



### **Introduction to payment forms: inline forms and checkout forms**

Now that the Stripe keys are set, you can create payment forms and subscription forms as well.  
  
Forms are available in two flavors: inline and checkout:  


* Inline forms are standard HTML forms, all fields rendered as part of your page.
* Checkout forms take advantage of [Stripe Checkout](https://stripe.com/docs/checkout) functionality which will give you the option to place a button on any post or page. The button will trigger loading of a pre-styled form with built in validation hosted by Stripe. The styling and functionality of the form is all controlled by Stripe and offers a fast and easy way to get started.

### **One-time payments**

You can create one-time payment forms on the "Full Stripe -&gt; Payments -&gt; Payment Forms" page.  
A payment form is set up to take a specific payment amount from your customers. Create the form by setting it's name, title and payment amount. You can also choose to allow your customers to enter custom amounts on the form, or to select the amount from a list. This makes creating things like donation forms easier. The form name is used in the shortcode \(see below\) to display the form.

{% hint style="info" %}
To show an inline payment form, add the following shortcode to any post or page: `[fullstripe_form name="formName" type="inline_payment"]` where "formName" equals the name you used to create the form.
{% endhint %}

{% embed url="https://youtu.be/cfr\_MtcP0Zs" %}





To show a checkout payment form, add the following shortcode to any post or page: `[fullstripe_form name="formName" type="popup_payment"]` where "formName" equals the name you used to create the form.

Once a payment is taken using the form, the payment information will appear on the "Full Stripe -&gt; Payments -&gt; Payments" page as well as on your Stripe Dashboard.

### **Subscriptions**

Similar to one-time payments, you can sign customers up for recurring subscriptions using a subscription form. Before creating a subscription form, you will need to create a subscription plan. You can do this from the "Full Stripe -&gt; Subscriptions -&gt; Subscription Plans" page.

When creating a subscription form, you choose the name, title and plans that you wish to offer your customers.

{% hint style="info" %}
To show an inline subscription form, add the following shortcode to any post or page: `[fullstripe_form name="formName" type="inline_subscription"]` where "formName" equals the name you used to create the form.
{% endhint %}

{% hint style="info" %}
To show a checkout subscription form, add the following shortcode to any post or page: `[fullstripe_form name="formName" type="popup_subscription"]` where "formName" equals the name you used to create the form.
{% endhint %}



You can view your list of subscribers on the "Full Stripe -&gt; Subscriptions -&gt; Subscribers" page or directly on the [Stripe Dashboard](https://manage.stripe.com/)

You can also cancel subscriptions on the "Subscribers" page.  




### **Subscriptions ending automatically - Payments in installments**

You can create subscriptions ending automatically after a certain number of charges.  
As an example, your customers could pay for your consulting or courses in installments.

In order to do this, create a subscription plan with the "Payment cancellation count" option set to the number of charges after which the subscription should end, and use this plan on the subscription form.

IMPORTANT: Make sure that webhooks are set up properly, otherwise this functionality will not work.

### **Collecting VAT on subscriptions**

You can add VAT to subscription charges.  
VAT is added to both the recurring fee and the setup fee.

You can set the VAT rate on the "Finance" tab of the subscription form.  
The VAT rate calculation strategy can be:

1. No VAT - No VAT is added, the "tax\_percent" Stripe property is not set.
2. Fixed rate - A fixed percentage of the net amount is added as VAT, the "tax\_percent" Stripe property is set accordingly.

### **Payment Currency**

The currencies Stripe supports depend on where your business is located. If you select a country/currency combination that Stripe does not support then the payment will fail.

Please refer to the [Stripe documentation](https://support.stripe.com/questions/which-currencies-does-stripe-support) for more details.

### **Custom Fields**

You can collect extra pieces of information from your customer, and store them in custom fields. When creating a form, you can choose to create 10 custom form fields. The custom fields will be appended to the payment information and viewable in your Stripe dashboard once the payment is complete.

### **Coupons**

You can accept coupon codes with subscriptions. First you must create the coupon in your Stripe dashboard. When creating your subscription forms you can turn on the option to allow a coupon code, and if the customer adds the correct code this will be applied to their payment\(s\).

### **Email Receipts**

{% hint style="danger" %}
**Make sure to setup your emails first. Contact us for help**
{% endhint %}

All payment forms can send customized email notifications.  
Payment forms can send a payment receipt.  
Subscription forms can send a subscription receipt, and a notification when a subscription has ended.  
  
You have some placeholder tokens that can be placed in the email HTML, and WP Full Stripe will substitute the relevant values. The tokens that can be used are:

* **`%AMOUNT%`** - Gross payment amount. On one-time payment forms, it's the payment amount. On subscription forms, it's the sum of plan amount and setup fee.
* **`%PRODUCT_NAME%`** - The name of the selected payment option \(payment forms only, used when payment type is "Select Amount from List"\)
* **`%SETUP_FEE%`** - Gross amount of the subscription's setup fee \(subscription forms only\)
* **`%SETUP_FEE_GROSS%`** - Gross amount of the subscription's setup fee \(subscription forms only\)
* **`%SETUP_FEE_NET%`** - Net amount of the subscription's setup fee. Equals to the gross amount if no VAT is applied, or the VAT rate is 0%. \(subscription forms only\)
* **`%SETUP_FEE_VAT%`** - VAT amount of the subscription's setup fee. It's zero if no VAT is applied, or the VAT rate is 0%. \(subscription forms only\)
* **`%SETUP_FEE_VAT_RATE%`** - VAT rate of the subscription's setup fee. It's zero if no VAT is applied, or the VAT rate is 0%. \(subscription forms only\)
* **`%PLAN_NAME%`** - The name of the subscription plan \(subscription forms only\)
* **`%PLAN_AMOUNT%`** - Gross amount of the subscription plan \(subscription forms only\)
* **`%PLAN_AMOUNT_GROSS%`** - Gross amount of the subscription plan \(subscription forms only\)
* **`%PLAN_AMOUNT_NET%`**- Net amount of the subscription plan. Equals to the gross amount if no VAT is applied, or the VAT rate is 0%. \(subscription forms only\)
* **`%PLAN_AMOUNT_VAT%`** - VAT amount of the subscription plan. It's zero if no VAT is applied, or the VAT rate is 0%. \(subscription forms only\)
* **`%PLAN_AMOUNT_VAT_RATE%`** - VAT rate of the subscription plan. It's zero if no VAT is applied, or the VAT rate is 0%. \(subscription forms only\)
* **`%INVOICE_URL%`** - URL of the PDF invoice issued for the initial payment of a subscription
* **`%NAME%`** - The name of your Yovale website
* **`%CUSTOMERNAME%`** - The customer's cardholder name
* **`%CUSTOMER_EMAIL%`** - The customer's email address
* **`%ADDRESS1%`** - The customer's billing address line 1 \(street\)
* **`%ADDRESS2%`** - The customer's billing address line 2
* **`%CITY%`** - The customer's billing address city
* **`%STATE%`** - The customer's billing address state \(or region/county\)
* **`%ZIP%`** - The customer's billing address zip \(or postal code\)
* **`%COUNTRY%`** - The customer's billing address country
* **`%CUSTOMFIELD1%`** - Token for the 1st custom field of the form
* **`%CUSTOMFIELD2%`** - Token for the 2nd custom field of the form
* **`%CUSTOMFIELD3%`** - Token for the 3rd custom field of the form
* **`%CUSTOMFIELD4%`** - Token for the 4th custom field of the form
* **`%CUSTOMFIELD5%`** - Token for the 5th custom field of the form
* **`%CUSTOMFIELD6%`** - Token for the 6th custom field of the form
* **`%CUSTOMFIELD7%`** - Token for the 7th custom field of the form
* **`%CUSTOMFIELD8%`** - Token for the 8th custom field of the form
* **`%CUSTOMFIELD9%`** - Token for the 9th custom field of the form
* **`%CUSTOMFIELD10%`** - Token for the 10th custom field of the form
* **`%DATE%`** - The date on which the email notification is sent 

### **Redirects and confirmation \("Thank you"\) pages**

After a successful payment, the plugin can redirect to any page, post, or external URL known as the confirmation \("Thank you"\) page.

You can enable redirects on a form by:

1. Setting the "Redirect on Success?" option to "Yes"; and
2. Setting the page or post in the "Redirect to" option.

You can use placeholder tokens on "Thank you" pages, similar to email receipts.  
It can be turned on by checking the "Enable placeholder tokens on Thank You pages?" option of the form.  
  
When placeholder tokens are allowed on a Thank you page, then payment-related information can be displayed only once, after having redirected from the payment page.

Use the following shortcodes on a Thank you page to display payment-related information:

```text
        [fullstripe_thankyou]
        [fullstripe_thankyou_success]
		Thank you for your purchase, %CUSTOMERNAME%!
        [/fullstripe_thankyou_success]
        [fullstripe_thankyou_default]
		No payment data available
        [/fullstripe_thankyou_default]
        [/fullstripe_thankyou]
```

You can use the `[fullstripe_thankyou]` shortcode to mark the area where you'd like the payment information to be displayed.  
  
Inside `[fullstripe_thankyou]`, use the `[fullstripe_thankyou_success]` shortcode to display payment-related data \(see the Email Receipts section for the placeholder tokens\), and use `[fullstripe_thankyou_default]` to display feedback to the user when the Thank you page has been called directly.  





# Change Datacenter Location

{% hint style="info" %}
By default, your websites are hosted on Global infrastructure powered by AWS. However, if your business works in a specific country, you can choose the data center location for your website. 
{% endhint %}

{% hint style="warning" %}
Changing location can take up to 24 hours. 
{% endhint %}

{% hint style="success" %}
Changing datacenter location is easy and requires you to change/add/replace a CNAME record in your Cloudflare DNS settings.
{% endhint %}

List of Datacenters and required DNS records-

{% hint style="info" %}
Change the Host value as required
{% endhint %}

| LOCATION | TYPE | HOST | VALUE |
| :--- | :--- | :--- | :--- |
| Global \(default\) | CNAME | @ | `connect.serverlessinfra.com` |
| US East \(Ohio\) | CNAME | @ | `us-east-2.serverlessinfra.com` |
| US East \(N. Virginia\) | CNAME | @ | `us-east-1.serverlessinfra.com` |
| US West \(N. California\) | CNAME | @ | `us-west-1.serverlessinfra.com` |
| Africa | CNAME | @ | `af-south-1.serverlessinfra.com` |
| Asia Pacific \(Hong Kong\) | CNAME | @ | `ap-east-1.serverlessinfra.com` |
| Asia Pacific \(Mumbai\) | CNAME | @ | `ap-south-1.serverlessinfra.com` |
| Asia Pacific \(Singapore\) | CNAME | @ | `ap-southeast-1.serverlessinfra.com` |
| Asia Pacific \(Sydney\) | CNAME | @ | `ap-southeast-2.serverlessinfra.com` |
| Asia Pacific \(Tokyo\) | CNAME | @ | `ap-northeast-1.serverlessinfra.com` |
| Canada \(Central\) | CNAME | @ | `ca-central-1.serverlessinfra.com` |
| ~~China \(Beijing\)~~ | ~~CNAME~~ | ~~@~~ | ~~`cn-north-1.serverlessinfra.com`~~ |
| ~~China \(Ningxia\)~~ | ~~CNAME~~ | ~~@~~ | ~~`cn-northwest-1.serverlessinfra.com`~~ |
| Europe \(Frankfurt\) | ~~CNAME~~ | @ | `eu-central-1.serverlessinfra.com` |
| Europe \(Ireland\) | CNAME | @ | `eu-west-1.serverlessinfra.com` |
| Europe \(London\) | CNAME | @ | `eu-west-2.serverlessinfra.com` |
| Europe \(Milan\) | CNAME | @ | `eu-south-1.serverlessinfra.com` |
| Europe \(Paris\) | CNAME | @ | `eu-west-3.serverlessinfra.com` |
| Europe \(Stockholm\) | CNAME | @ | `eu-north-1.serverlessinfra.com` |
| Middle East  | CNAME | @ | `me-south-1.serverlessinfra.com` |
| South America \(São Paulo\) | CNAME | @ | `sa-east-1.serverlessinfra.com` |

{% hint style="danger" %}
Data center location in China is not available due to some legal issues. 
{% endhint %}


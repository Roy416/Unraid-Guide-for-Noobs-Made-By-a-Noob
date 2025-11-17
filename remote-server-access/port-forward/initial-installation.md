# ⬇️ Initial Installation

{% hint style="info" %}
[Accompanying video by IBRACORP](https://www.youtube.com/watch?v=c6Y6M8CdcQ0)
{% endhint %}

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f511">🔑</span> <strong>Key Term - Port Forwarding</strong></summary>

* **When you port forward something**, you’re opening a port, aka **creating an** **access point**. This access point allows you to access your services when you’re in the outside world.
* However, since you’re able to connect to the access point from the outside world, there is a potential that a hacker can do the same.
* Of course, there are ways to **secure the ports** and **minimize the threat**, but **some part of the threat will still remain**.

</details>

**Note**<mark style="color:red;">**:**</mark> <mark style="color:red;"></mark><mark style="color:red;">Cloudflare is constantly changing their website layout, so in the future these steps may not exactly depict what to do, but the same stuff needs to be done nonetheless.</mark>&#x20;

1. **Buy a domain** from a registrar of your choice.
2. **Sign up with Cloudflare** using a free account, enter your domain, and it should prompt you to do a quick scan for DNS records.&#x20;
3. After the scan, the DNS records page should appear. If not, on the bar on the left, click DNS and then Records. This page lets you create URLs and connects them to your server, we will come back to this later. Click continue.&#x20;
4. It'll now ask you to **replace your domain registrar's nameservers** with Cloudflare's own nameservers. <mark style="color:red;">What is a nameserver</mark>
5. Go to your **domain registrar's settings** and find the **DNS section**. Next, it should say somewhere to use custom nameservers. Add both of the nameservers that Cloudflare gave.&#x20;
6. Then go back to Cloudflare and **click "Done, check nameserver**s." This could take a few mins to 30 minutes, or even longer.&#x20;

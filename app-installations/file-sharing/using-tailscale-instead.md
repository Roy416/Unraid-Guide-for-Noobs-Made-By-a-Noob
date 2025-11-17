# 🕸️ Using Tailscale Instead

{% hint style="info" %}
[Accompanying video by Spaceinavder](https://www.youtube.com/watch?v=FU1vdM4dIhY\&t)
{% endhint %}

Unfortunatley Nextcloud AIO requires a domain. So instead of purchasing a domain, you can use your Tailscale domain instead. Currently if you type in your Tailscale IP (e.g. unraidserver.fox-garibaldi.ts.net), it would take you to your Unraid server. What we plan to do is redirect this URL to Nextcloud. You're probably thinking, "But what if i want to view the Web UI with the Tailscale IP?" You will still be able to, but you'll have to add an extra port at the end when inputting the IP in your browser.&#x20;

{% embed url="https://docs.google.com/presentation/d/1fCiga-cQ6A0OLqvdjC1TsSz9giYZYSV5P_9IyBdf8_8/edit?usp=sharing" %}

1. Go to **Settings -> Management Access** and you will see your **Tailscale URL**. If you type this URL it will take you to the Unraid Web UI.&#x20;
2. **Open the terminal** and enter  `tailscale serve --bg --https=443 http://127.0.0.1:11000` . Now your Tailscale IP will redirect to Nextcloud. However, if you were to restart your server, this command wouldn't be in effect. So lets fix that.&#x20;
3. Go to Apps and **download User Scripts**.&#x20;
4. Go to **Settings -> User Scripts** -> **click Add New Script** and give it a name.&#x20;
5. Copy the command in Step 2, and then **click on the cog of the script you just created -> click edit script -> paste the command** under #!/bin/bash. **Click Save Changes**
6. Then on the right, **change "Schedule Disabled" to "At First Array Start Only"**. Now that's sorted, but we didn't fix how you'll be able to reach the Unraid Web UI yet, so let's do that.
7. Go to **Settings -> Management Access**.
8. Change the HTTPS Port from **443 to 4443**.&#x20;
9. Now if you enter your Tailscale IP with 4443 at the end (e.g. unraidserver.fox-garibaldi.ts.net:4443), the Unraid Web UI should appear. &#x20;

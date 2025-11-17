# 🫴 Giving Access

1. Note the Web UI port of the container you want access to be given to
2. Open Nginx Proxy Manager, then go to Proxy Hosts, and click Add Proxy Host.&#x20;
3. Add what your website should be, for example, overseer.domain.com. Make sure to click add, sometimes it doesn't enter properly.&#x20;
4. Majority of the containers use http. Some may use https like nextcloud. <mark style="color:$danger;">Whether or not you should use http vs https depends on the app. Most of them use http, but some do use https, for example Nextcloud.</mark>
5. Then enter your server ip for the forward hostname and the web ui port of the container for the forward port.&#x20;
6. You can enable all of cache assets, block common exploits, and <mark style="color:red;">websockets support</mark>. Websockets support isn't necessary for most apps,&#x20;
7. Click SSL, and choose your custom certificate. Also enable Force SSL, HTTP/2 Support, and HSTS Enabled. Both <mark style="color:red;">Websockets support and HSTS Enabled aren't necessary for every container,</mark>&#x20;
8. Now head on over to Cloudflare and its DNS Records. Click Add Record, change the type to CNAME, for name enter the subdomain, and for the ipv4 address its your domain.&#x20;
9. All done! Now try entering that URL in and hopefully you can see your container!&#x20;

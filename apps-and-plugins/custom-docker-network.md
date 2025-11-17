# 🕸️ Custom Docker Network

{% hint style="info" %}
[Accompanying video by IBRACORP](https://www.youtube.com/watch?v=3mlULdJmCf8\&t)
{% endhint %}

When you install an app, the default network type is `bridge` . However, you can create your own docker network. This is useful for 2 reasons:

1. **Name Resolution** - This means that apps on the same custom docker network, can refer to each other by name. This is really convenient, as currently if your server's IP address were to change for whatever reason (power outage, re plugging router, new ISP), you'd have to go through all your apps and update the IP's of the containers it needs to talk to (e.g. updating the IPs in Nginx Proxy Manager). But if it's referred to those containers by name, you don't gotta do a thang.&#x20;
2. **Security** - With all the apps under the same custom docker network, they can now talk to each other. But maybe you want to create separate groups so if a container in one group gets breached, it doesn't transfer to another group of containers. For example, having a custom network for all your media apps, another for Nextcloud, and another for Immich. To clarify, this is just planning for the worst-case scenario, it’s not something that normally happens.

### Creating a custom docker network&#x20;

1. Go to the terminal and enter `docker network create networkname` .&#x20;
2. You can check if it's been successfully created by entering `docker network ls` .

### Connecting a container to multiple networks

A container can be connected to multiple custom networks. This is super useful for reverse proxies. You can still separate your container into groups, but let NginxProxyManager have access to all groups, so it can refer to containers by name.&#x20;

Let's say you created a new custom network called games, and you want NginxProxyManager to have access to it.&#x20;

Go to the terminal and enter: `docker network connect games NginxProxyManager` , now a second custom network has been added to NPM.&#x20;

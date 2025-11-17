# Post Installation Setup

### Folderview2

First thing you probably said was "maan, this added like a gazillion containers on the docker tab making it all ugly." Luckily for you theres a plugin called folderview2. After installing it, you'll see a "Add-Folder" button below all your containers. So you can group those containers in a folder, give it a picture, rearrange the order, and customize the colours.&#x20;

### Mobile App

&#x20;If you're using a domain you purchased, enter your server URL with **https**, even though that's not what you put in NPM. If you're using a Tailscale address (e.g. 100.96.55.104) then you can keep it at http.&#x20;

### How to Update

Since we installed Immich through Docker Compose, we'll have to update it with a different way. It'll always show that an update is available but that isn't to be trusted, If you go onto your Immich instance, a pop up may appear saying that there's an update.&#x20;

This is where the "Update Stack" button comes in, which is next to the Immich stack you created. HOWEVER, I recommend reading Immich's Github page, in case there's anything you need to do in your end before updating. It rarely happens but just in case. I'm assuming we don't want to enable auto start on those containers as well.  &#x20;

### Nginx Proxy Manager Settings

Similar to what we did for Nextcloud [here](../file-sharing/post-installation-setup.md#nginx-proxy-manager-fix), you might want to do the same for Immich. I noticed Immich was loading slow at times with NPM, but after applying that, it became super speedy. &#x20;


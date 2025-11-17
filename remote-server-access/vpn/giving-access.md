# 🫴 Giving Access

Currently you can access all your services from any of your device that you've logged in and setup Tailscale on. You could invite someone to your tailscale network, however, that will mean they will have access to all of your services, server files, and your home network. What if there was a way to invite someone but only have access to a specific container?&#x20;

**Note:** I haven't gotten this to work for Plex or Nextcloud (google drive alternative). &#x20;

### TSD + Label  Manager

This is the method which the creator of the Tailscale plugin created and recommends. Currently it doesn't support TCP/UDP stuff which is necessary for giving access to game servers.&#x20;

1. **Download TSD Proxy** and **Label Manager**.
2. Go to **Settings** → **Users Utilities** → **Label Manager**.&#x20;
3. Go to the running container you want, click Edit, and Select Yes.&#x20;
4. Open the Web UI for TSD Proxy. It'll show "authenticating" for the container you just added. Click on it, click connect, click "Open in admin console", and click Approve. If nothing shows up on TSD Proxy, try checking if the container you're trying to add. It might have stopped so try restarting it.&#x20;
5. Now go to the Admin Console on Tailscale, and you'll see the container you just added as a device. Where you can share it to someone.&#x20;

dfdfdfffdf. for qbittrent/ sab/stuff with different internal ports you have to add 8080. for immich since we added that through docker compsoe file, copy and paste the lines you added to the compose here.&#x20;

for nextcloud the port is 11000 for the master container, make it https, add it to the config of nextcloud and add nextcloud-aio network to tsdproxy.&#x20;

<details>

<summary>Tailscale Integration Switch</summary>

With the 7.0 update, containers have tailscale integration builtin within their settings.&#x20;

1. Right click on a container, and click edit.&#x20;
2. Turn on "Use Tailscale"
3. Enter a name for it in "Tailscale Hostname". This is what will appear as the device name on your Tailscale network. And click Apply.&#x20;
4. Open the logs of the container, and it'll ask you to click on a link to authenticate. After clicking connect, click "Open in admin console", and click Approve.&#x20;
5. Now you can connect to it by using the tailscale address with all letters.

</details>

# ⬇️ Installation

{% hint style="info" %}
[Accompanying video by DiGi-Sun](https://www.youtube.com/watch?v=TBnuyYUDiOw)
{% endhint %}

A media server is something that stores your tv shows and movies, legally obtained of course. We will be installing **Plex**. Plex also stores photos and music, but there are better options for those.&#x20;

{% embed url="https://docs.google.com/presentation/d/1AP16VExgDxzZyMjaPy5jVnPM0I8hgf_9NyLmYD5m5KU" %}

1. Go to **Shares -> appdata**, and **create a folder** called **transcode**. We will use this shortly.&#x20;
2. **Download Plex** from the official maintainer. I found this template to work the most seamlessly.&#x20;
   1. One thing you'll notice is that the bridge mode is "Host". This isn't ideal, but most templates for Plex have it as Host, so what can ya do 🤷‍♂️.&#x20;
3. **Select the transcode folder** that you made in step 1. This will serve as a temporary location when Plex transcodes. And **select the share** with all your media (make sure there is a / at the end). If you're using TRaSH, select the media folder. Click **Apply**.&#x20;
   1. If you want to add a media path that's in a different share, scroll down and click "Add another Path, Port, Variable, Label or Device". Give it a container name (this is how it will show in Plex) and set the host path to the actual path of the share.&#x20;
4. It'll take a moment. Click "**Got it**" and **give your server a name**. Click **Next**.
5. Click **Add Library**. Choose the **type of media** you want to add, and you can customize the name.&#x20;
6. Click **Add folders**, **Browse for Media**, and click on the **data folder** on the left. Then on the right, select the folder your type of media is in.&#x20;
7. Repeat this for all different types of media.&#x20;
   1. Note, you can add multiple libraries of the same type of media (e.g. adding a separate shows library for anime).

### :fast\_forward: Portforwarding Plex

Port forwarding for Plex is very simple. Simply use “32400” for both the internal and external ports, and enter the IP of your Unraid server.




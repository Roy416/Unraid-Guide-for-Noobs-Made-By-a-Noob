# 💾 External Storage

External Storage allows you to connect a share to Nextcloud. This is useful when you want to share a file to someone is already in one of your shares, rather than having to first copy and paste that into Nextcloud.&#x20;

{% embed url="https://docs.google.com/presentation/d/1AINoRvI6qYnDWNEASlY5avH-Z45MlmnEo35uWhc7xO4/edit?usp=sharing" %}

1. Click edit on the nextcloud-aio-mastercontainer.
2. Scroll down and click **"Add another Path, Port, Variable, Label or Device"**
3. Change the **Config Type to Variable** and set the **Name and Key** to `NEXTCLOUD_MOUNT` and the **value** to `/mnt/user/`  and click Save. **THIS IS A SECURITY HAZARD DONT DO THIS. ADD EACH SHARE SEPREATEY.**&#x20;
4. Go to your **profile -> Administration Settings -> Overview** (under Administration) **-> Open Nextcloud AIO Interface -> Click Stop Containers**. Once they're all stopped, **start them again**.&#x20;
5. Once all the container are started, Go to your **profile -> Administration Settings -> External Storage** (under Administration). If you don't see external storage there, you might have to enable it under Apps.&#x20;
6. Give the folder a **name**, and change **Add Storage to Loca**l.&#x20;
7. **Set the location** to /mnt/user/YOUR\_SHARE (e.g. /mnt/user/books).
8. **Select All People**, click on the check mark, and enter your password. You should see a green indication.&#x20;
9. To be able to share files from this share, **click on the three dots and select Enable sharing**. There's also the option to enable Read Only which could be useful when adding other people to your Nextcloud Instance.&#x20;

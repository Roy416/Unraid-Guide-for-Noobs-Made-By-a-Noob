# 🗺️ Mapping Shares

{% hint style="info" %}
[Accompanying video by TechnGo](https://youtu.be/PePFc-eQCsY?si=_V3pszyVh35g5s3F\&t=165)
{% endhint %}

### 🪟 Mapping Shares on Windows

Here are all the ways you can map your shares on Windows:

1. Open **File Explorer** → click **This PC** → click on the **3 dots** at the top → click **Add Network Location** → Enter `\\<server ip>\<share name>` (ignore the arrows). You could also click "Add Network Drive" instead of location, if you so choose.&#x20;
2. Open **File Explorer** → click **Network**, and your server should be there.

### 🍎 Mapping Shares on MacOS&#x20;

### 🚫Error with Connecting?

If you're having trouble trying to your private/secure share, Here are some things you can try.&#x20;

**Refresh the permissions of the shares:** &#x20;

1. Go to the **Tools** tab.
2. Select **New Permissions**.
3. Change the setting from **Disks** to **Shares**.
4. Only choose the **problematic shares** and click **Start**.

If that doesn’t work, some other things you can try are:

* Restarting your PC
* Restarting SMB by clicking on the terminal (the **>\_** on the top right of the Web UI) and type `/etc/rc.d/rc.samba restart`  and restart your PC.
* Delete your login in the Windows Credential Manager ([shown here](https://youtu.be/PePFc-eQCsY?si=vihJ6fif8Plc-pzP\&t=167)), and restart your PC.

Another tip a user suggested was using the same user name and password as your windows login for your new Unraid user.

### My Personal Experience

In my personal experience, the most **error-free way** to link your shares to your PC is through **network&#x20;**_**location**_ and selecting **“Remember my credentials”** (<mark style="color:$danger;">this will only appear if you don’t set up your login with windows credentials).</mark> is trying to say:\
👉 The “Remember my credentials” checkbox only shows up if your Windows login is different from the credentials of the share you’re connecting to.

# 📫 Post Installation Setup

### :no\_entry\_sign: Disabling Apps

There may me some features that are installed by default that you might not use. On the top right click on your profile -> apps -> your apps, and disable whatever you want.&#x20;

### :lock\_with\_ink\_pen: Change Password/New Account

To change your password:

1. Click your profile on the top right and click Account.
2. Click on the pencil edit icon and enter a new password. Make sure to click the little arrow first and not the check mark on the far right.&#x20;

You won't be able to change the username. Instead you'd have to create a new account, log into that one, then delete the original admin account. On that same account page:

1. Click New Account on the top left and enter the account name, password and set the groups to admin. then login to that account, and you can delete the admin account.

### :mobile\_phone: Enable 2FA

To enable 2FA:

1. Click on your profile -> Administration Settings -> Security
2. Toggle "Enforce two-factor authentication", and add admin to the enforced groups, click Save Changes.
3. Then scroll up on the left, and click Security under the Personal header, and enable TOTP.&#x20;

If you enabled Collabora when installing, you need to do something in order to get it to work.&#x20;

1. Click on your profile -> administration settings -> office (under administration)
2. Find "Allow list for WOPI requests" and remove everything, and click save.&#x20;

HOW TO UPDATE IT GO INTO THE ADMIN PANEL STOP AND START

### :spider\_web: NGINX Proxy Manager Fix

With NPM, Nextcloud can be fussy. After I added this to NPMs settings for Nextcloud, the issues stopped happening.&#x20;

Go to NPM -> edit the entry for Nextcloud -> go to Advanced and paste the following.&#x20;

```
client_body_buffer_size 512k; 
proxy_read_timeout 86400s; 
client_max_body_size 0;
```

You can go [here ](https://github.com/nextcloud/all-in-one/blob/main/reverse-proxy.md#nginx-proxy-manager---npm)for more info.&#x20;

### :desktop: Desktop Client

Lastly, you can install Nextcloud on your computers and phone. So whenever you save a document in the Nextcloud folder, it'll be backed up to your server. You can choose that all the Nextcloud files are also synced to your computer, creating another copy of your files.&#x20;

### Mobile App

Nextcloud does have a mobile app where you can view your files. However, the **one issue with the app is, if you want to view something, it will download it in the cache on your phone.** Meaning, if you view 100 photos, it will download the 100 photos on your phone, taking up space, until the app deletes it a week later. Which is why it's not ideal for it to be used to back up your mobile photos. &#x20;


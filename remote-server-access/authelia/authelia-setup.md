{% hint style="info" %}
[Accompanying video by AlienTech42](https://www.youtube.com/watch?v=LRFwjATqFdw&t=)
{% endhint %}

<style>
.my-text { color: #000; }
html.dark .my-text { color: #eee; }
</style>

<div class="my-text">

### ⬇️ Setting up configuration files

1. **Install** the official container of Authelia. If you're using custom docker networks and using port forwarding, make sure it's on a network that Nginx Proxy Manager has access to.
2. Open the **Unraid terminal** and run this command. This will create three random strings. Keep these on a temporary notepad:
```
for i in 1 2 3; do openssl rand -base64 32; done
```
3. Enter the command below. This will create a random password and a "Digest". The random password being the **password to your Authelia account**. Keep both of these in a temporary notepad as well. This will also create a container with a funny name, you can delete it after. 
```
docker run --rm authelia/authelia:latest authelia crypto hash generate argon2 --random --random.length 64 --random.charset alphanumeric
```
4. **Download** these files. They are based off of [AlienTech42's configs](https://github.com/AlienTech42/unraid-config-files/tree/main/authelia):

[!file icon="rocket" text="configuration.yml"](../../assets/configuration.yml)

[!file icon="rocket" text="users_database.yml"](../../assets/users_database.yml)

5. Open **configuration.yml** with an editor. Replace all the sections that have `YOUR_DOMAIN` with your domain (e.g. https://nextcloud.example.com, the domain is `example`). A replace all feature would be handy here. 
6. There are 3 lines where you must replace `REPLACE_WITH_RANDOM_STRING` with the three random strings you created before. Under: 1) **session**, 2) **storage**, and 3) **identity_validation**. **Save** the file.
7. Open **users_database.yml**. Under users, **rename** `user` to what you want your login name to be. Replace the **password with the Digest** you created before. Change the display name and email. Click **Save**. 
    - By itself, `admins` in groups means nothing. This part of the Access Control Lists (ACL), for when you want only certain people to access the site. Refer to the subject section in [this configuration](https://www.authelia.com/configuration/security/access-control/#configuration).
8. Go to **Authelia's appdata** folder. **Delete** the configuration.yml that exists, and **upload** the configuration.yml and the users_database.yml that you just edited. **Restart** Authelia.

### 👁 Exposing Authelia
1. **Expose Authelia** as you normally would with either port forwarding or Cloudflare tunnel. The protocol is `http`, the port is `9091`, and set the subdomain to `auth`. 
2. Go to your **Authelia site** and login with the password you created in Step 3 above.
3. Click **Register device** and either select WebAuthn Credentials (passkey) or One-Time Password (authenticator app). It will ask for a one time password. Go to Authelia's appdata folder and open `notifications.txt` to get it.
4. Then depending on what you chose, continue setting up via an authenticator app or password manager. 

### 🤪 Authelia's Quirk

Even if you have 2FA enabled and you log into Authelia with just your user and password, it'll let you manage your devices without completing the 2FA. Which sounds kind of unsafe. Fortunately, if a person does guess your password, they can't really do anything since it requires them to have access to your server files to make any changes.

### 🖵 Blank Screen?
Sometimes when you log into your Authelia site and put your 2FA in, it'll give you a blank screen. In the URL field add the `auth.` back in front of your domain. For whatever reason it removes it. Then you'll be able to manage your devices.

</div>

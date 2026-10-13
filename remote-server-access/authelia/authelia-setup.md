---
label: Installation
order: 980
icon: 
---
{% hint style="info" %}
[Accompanying video by AlienTech42](https://www.youtube.com/watch?v=LRFwjATqFdw&t=)
{% endhint %}
   
### Setting up configuration files

1. Install Authelia. if you're using custom docker networks, make sure it's on a network that NginxProxyManager has access to.
2. Open the Unraid terminal and run this command. This will create three random strings. Keep these on a temporary notepad:
```
for i in 1 2 3; do openssl rand -base64 32; done
```
3. Now enter the command below. The random password is the password to your Authelia account. Keep both of these in a temporary notepad as well. This will also create a container with a funny name, you can delete it after. 
```
docker run --rm authelia/authelia:latest authelia crypto hash generate argon2 --random --random.length 64 --random.charset alphanumeric
```
4. Download these files. They are based off of [AlienTech42's configs](https://github.com/AlienTech42/unraid-config-files/tree/main/authelia):

[!file icon="rocket" text="configuration.yml"](../../assets/configuration.yml)

[!file icon="rocket" text="users_database.yml"](../../assets/users_database.yml)

5. Open configuration.yml with an editor. Replace `YOUR_DOMAIN` with your domain (e.g. https://nextcloud.example.com, the domain is example). A replace all feature would be handy here. 
6. There are 3 lines where you must replace `REPLACE_WITH_RANDOM_STRING` with the three random strings you created before. Under:
    - session, secret.
    - storage, encryption_key.
    - identity_validation, jwt_secret.
    - Save the file.
7. Open users_database.yml. Under users, rename `user` to what you want your login name to be. Replace the password with the Digest you created before. And change the display name and email. Click Save. 
    - By itself, `admins` in groups means nothing. This is for Access Control Lists (ACL), for when you want only certain people to access the site. Refer to the subject section in [this configuration](https://www.authelia.com/configuration/security/access-control/#configuration)
8. On Unraid go to Authelia's appdata folder. Delete the configuration.yml that exists, and upload the configuration.yml and the users_database.yml you just edited. Restart Authelia.

### Exposing Authelia
1. Expose Authelia as your normally would with either portforwarding or cloudflare tunnels. The protocol is `http`, the port is `9091`, and set the subdomain to `auth`. 
2. Go to your Authelia site, login with the password you created in step 3 above.
3. Click Register device and either select WebAuthn Credentials (passkey) or One-Time Password (authenticator app). It will ask for a OTP. Go to the appdata folder for Authelia and open `notifications.txt` to get it.
4. Then depending on what you chose, continue setting up via authenticator app or password manager. 

Sometimes when you log into your authelia site and put your 2FA in, it'll give you a blank screen. In the url field add the `auth.` back in infront of your domain, for whatever reason it removes it. Then youll be able to manage your devices.

Even though you have 2FA enabled, if you log into Authelia with just your user and password, it'll let you manage your devices without completing the 2FA. Fortunatley, if a person does get in, they can't really do anything, since it requires them to have access to your server files to make any changes.








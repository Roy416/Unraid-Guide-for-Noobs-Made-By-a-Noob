---
label: Authelia Setup
order: 980
icon: ../../assets/shield.png
---

<style>
.my-text { color: #000; }
html.dark .my-text { color: #eee; }
</style>

<div class="my-text">

Things might update and change. Refer to [Authelia's Unofficial instructions](https://www.authelia.com/integration/openid-connect/clients/nextcloud/) if you're having trouble.

1. Set up [OIDC for Authelia](../../remote-server-access/authelia/oidc.md) if you havent already. 
2. Go to **Authelia's appdata** folder and open the **configuration.yml**. Scroll down until you see `clients`. Delete the hashtags for the client header and the nextcloud section.
3. Open the **terminal** and run the command below:  

```
docker run --rm authelia/authelia:latest authelia crypto hash generate pbkdf2 --variant sha512 --random --random.length 72 --random.charset rfc3986
```
4. This created a random password and a Digest. Paste the **Digest password** in the **client secret** field (within the quotes). 
5. Under `redirect_uris`, replace **YOUR_DOMAIN** with your domain. **Save** the file and **restart** Authelia.
6. Go to **Nextcloud** and install the app called `OpenID Connect user backend`. 
7. Go to your **profile** -> **administration settings** -> **click OpenID Connect** (under administration) and click add a **Registered Provider**. 
8. Enter the following fields:

| Field | Value  | 
| --------- | --------- | 
| Identifier   | Authelia    |     
| Client ID    | nextcloud   |
| Client secret | The random password from Step 3             |
| Discovery endpoint   | https://auth.YOUR_DOMAIN.com/.well-known/openid-configuration - Add your domain   | 
| Scope    | openid email profile groups   |    
| Attribute Mapping   | preferred_username     |     
| Authentication and Access Control Settings    | Uncheck use unique user ID    |

9. **Log out** of Nextcloud and try log back in, and you'll see a Login with Authelia button now!
10. If you want to remove the regular login, type this in the terminal: 
```
sudo docker exec --user www-data nextcloud-aio-nextcloud php occ config:system:set hide_login_form --type=boolean --value=true
```


</div>




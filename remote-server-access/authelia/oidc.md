---
label: OIDC Setup*
order: 925
icon: ../../assets/card.png
---
<style>
.my-text { color: #000; }
html.dark .my-text { color: #eee; }
</style>

<div class="my-text">

[!badge text="Note" variant="danger"] Only set this up, if you are planning to add a client right after. Because if you set this up and don't have an app to use it, **Authelia won't start**. This only has to be set up once.

### 🛠️ Setting up OIDC

1. Open configuration.yml and scroll down until you see `identity_providers`. I've pasted this section beforehand to avoid you the trouble of messing with indentations. Simply remove the hashtags. 

2. To get the **HMAC secret**, open the **terminal**, type the command below and paste it in the `hmac_secret` field:
```
docker run --rm authelia/authelia:latest authelia crypto rand --length 64 --charset alphanumeric
``` 
3. Type `cd /mnt/user/appdata/Authelia` to get into Authelia's Appdata folder and type this: 
```
docker run --rm -u "$(id -u):$(id -g)" -v "$(pwd)":/keys authelia/authelia:latest authelia crypto pair rsa generate --directory /keys
``` 
4. This created a private.pem file in Authelia's appdata folder. **Copy the contents** in the private.pem file and paste it under key. It's **crucial for the identation** to be the same as the example text.
5. Now continue with the installation instructions for the app you wanted to add to Authelia with OIDC. 


### 🩹 Disabling a Workaround

For some apps including Nextcloud and Immich, you can add `?direct=1` to the end of the URL and it'll bypass Authelia's authentification and let you login with the sites native login, which is very silly. To disable this, go into **Advanced settings** ( the cog) for a proxy in NPM and add: 

```
if ($arg_direct = "1") {
    return 403;
}
```

</div>


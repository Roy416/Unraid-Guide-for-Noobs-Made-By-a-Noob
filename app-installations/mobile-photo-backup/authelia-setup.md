<style>
.my-text { color: #000; }
html.dark .my-text { color: #eee; }
</style>

<div class="my-text">

Things might update and change. Refer to [Authelia's Unofficial instructions](https://www.authelia.com/integration/openid-connect/clients/immich/) if you're having trouble.

1. Set up [OIDC for Authelia](../../remote-server-access/authelia/oidc.md) if you havent already. 
2. Go to **Authelia's appdata** folder and open the **configuration.yml**. Scroll down until you see `clients`. Delete the hashtags for the client header and the immich section.
3. Open the **terminal** and run the command below:  

```
docker run --rm authelia/authelia:latest authelia crypto hash generate pbkdf2 --variant sha512 --random --random.length 72 --random.charset rfc3986
```
4. This created a random password and a Digest. Paste the **Digest password** in the **client secret** field (within the quotes). 
5. Under `redirect_uris`, replace **YOUR_DOMAIN** with your domain. **Save** the file and **restart** Authelia.
6. Go to **Immich** -> **Administration** -> **Authentication Settings** -> **OAuth**. Toggle login with OAuth if it isn't enabled already. 
7. Enter the following fields:

| Field | Value  | 
| --------- | --------- | 
| issuer_url  | https://auth.YOUR_DOMAIN.com   |     
| client_id    | nextcloud   |
| client_secret | The random password from Step 3             |
| token_endpoint_auth_method  | client_secret_basic   | 
| Button text    | Login with Authelia   |    

7. You can optionally enable Auto register and Auto launch. 

</div>

<style>
.my-text { color: #000; }
html.dark .my-text { color: #eee; }
</style>

<div class="my-text">

Now let's set up an app to use Authelia. If you're using Cloudflare tunnel, this requires you to set up Nginx Proxy Manager. This method is for apps that are only used through the web (not with desktop or mobile apps). 

0. In the configuration.yml, I set it up so every site that uses Authelia through NPM is automatically set to two factor authentication, so you don't have to edit the config every time. 
    - If you want to change this, remove the asterisk on line 33, and manually add in the sites that you want to use 2FA.
1. **Set up the remote access** for the app you want behind Authelia. If you're using Cloudflare tunnel, create a proxy for it within NPM too. 
2. In NPM, **edit the proxy**, click the **cog** on the top right, then **paste the script** below respective to the method you chose. Replace `SERVER_IP` and `YOUR_DOMAIN` with your own:

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f511">⏩</span> Port Forwarding</summary>

```
# Fix large cookie issues (Authelia)
client_header_buffer_size 16k;
large_client_header_buffers 4 32k;

# Enable Authelia authentication
auth_request /authelia;

# Internal Authelia verification endpoint
location = /authelia {
    internal;
    proxy_pass http://SERVER_IP:9091/api/verify;  # CHANGE
	
	# REQUIRED for Cloudflare Tunnel setups
    # Force HTTPS since Cloudflare terminates SSL

    proxy_set_header X-Original-URL $scheme://$host$request_uri;
    proxy_set_header X-Forwarded-Proto $scheme;

	# Forward client IP info to Authelia
	
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

    # Required for auth_request
    proxy_set_header Content-Length "";
	proxy_pass_request_body off;
}

# Redirect unauthenticated users to Authelia login
error_page 401 =302 https://auth.YOUR_DOMAIN.com/?rd=$scheme://$host$request_uri;  # CHANGE

</details>

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f511">☁️</span> Cloudflare Tunnels</summary>

```
# Fix large cookie issues (Authelia)
client_header_buffer_size 16k;
large_client_header_buffers 4 32k;

# Enable Authelia authentication
auth_request /authelia;

# Internal Authelia verification endpoint
location /authelia {
    internal;
    proxy_pass http://SERVER_IP:9091/api/verify;  # CHANGE

    # REQUIRED for Cloudflare Tunnel setups
    # Force HTTPS since Cloudflare terminates SSL

    proxy_set_header X-Original-URL https://$http_host$request_uri;
    proxy_set_header X-Forwarded-Proto https;

    # Pass real client IP from Cloudflare
    
    proxy_set_header X-Real-IP $http_cf_connecting_ip;
    proxy_set_header X-Forwarded-For $http_cf_connecting_ip;

    # Required for auth_request
    proxy_set_header Content-Length "";
    proxy_pass_request_body off;
}

# Redirect unauthenticated users to Authelia login
error_page 401 =302 https://auth.YOUR_DOMAIN.com/?rd=https://$http_host$request_uri;  # CHANGE
```

</details>

</div>

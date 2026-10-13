---
label: Forward Authentication
order: 930
icon: 
---


web app only
Now lets setup an app to use authelia. If you're using cloudflare tunnels, this requires you to set up Nginx Proxy Manager. 

0. In the configuration.yml by default, I made it so every site that uses Authelia through NPM is automatically set to two factored authenication, so you dont have to go into the config every time. 
    - If you want to change this, remove the asterix on line 33, and uncomment lines 45 and 46.
1. Set up your app for remote access. If you're using cloudflare tunnels, create a proxy for it within NPM too. 
2. Edit the proxy, click the cog on the top right, then paste the script below respective to the method you chose, replacing `SERVER_IP` and `YOUR_DOMAIN` with your own:

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
    proxy_pass http://SERVER_IP:9091/api/verify;

    proxy_set_header X-Original-URL $scheme://$host$request_uri;
    proxy_set_header X-Forwarded-Proto $scheme;

    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

    # Required for auth_request
    proxy_pass_request_body off;
    proxy_set_header Content-Length "";
}

error_page 401 =302 https://auth.YOUR_DOMAIN.com/?rd=$scheme://$host$request_uri;
```

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
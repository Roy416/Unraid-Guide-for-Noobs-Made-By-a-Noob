---
label: About Authelia
order: 1000
icon: ../../assets/info.png
---

<style>
.my-text { color: #000; }
html.dark .my-text { color: #eee; }
</style>

<div class="my-text">

Authelia is known as a SSO (Single Sign-On). It isn't necessary to set up right away, but it's the next step in security if you're accessing your apps remotely via port forwarding or cloudflare tunnel. If you're using Tailscale, you can ignore this, unless you don't trust the users you've given access to your tailnet. 

A SSO does two things:

1. Sets up **two factor authentication** for your sites. With either an authenticator app or passkey. 
2. Lets you **log in with the same username and password** across all your sites, hence *single sign-on*. 

There are two ways to set up Authelia for an app: **forward authentication** or **OIDC**. With forward authentication, the setup goes through NPM and is a lot easier. However, if the app has a mobile app or desktop client, this method usually won't work, which is where OIDC comes in.

OIDC is the built-in way for an app to use Authelia (and other services like it). Not all apps support OIDC, you can see the list [here](https://www.authelia.com/integration/openid-connect/clients/).

Some apps have 2FA built-in, such as Nextcloud, which takes seconds to set up. So if you only need 2FA for Nextcloud for example, you could skip setting up Authelia. 

If you're using Cloudflare Tunnel, OIDC doesn't require a reverse proxy, whereas forward authentication does.

</div>





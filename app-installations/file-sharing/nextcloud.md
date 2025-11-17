---
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# 📁 Nextcloud

For our purposes, Nextcloud is a Google Drive replacement where you can share files, sync documents, and a lot more. You can also install apps within Nextcloud that offer more functionalities. There are two versions of it, the bare bones version and the AlO (All In One) version. I've used the bare bones version for a while and it does give me some problems from time to time.&#x20;

As the name suggests, the All In One version includes everything you need, the install is much easier, and supposedly requires no maintenance. However it does require a domain. There is a roundabout way to make it work with use a tailscale domain, which I'll also show.&#x20;

Nextcloud gets a bad wrap for being bloated and being fussy . So many people set out for an alternative but return back to Nextcloud. Hopefully the AIO version is smoother sailing than the barebones.&#x20;

### Alternatives

<table><thead><tr><th width="112.20001220703125"></th><th></th></tr></thead><tbody><tr><td>Seafile</td><td><p>Probably the closest to Nextcloud in terms of basic functionality. Super efficient file syncing, so good for a lot of files. More finicky to install. </p><p>Your files are stored as little chunks in its database, so you aren't able to see your files straight up on your server. But you can run a script and use rsync to copy your files into a share as a workaround.</p></td></tr><tr><td>Syncthing</td><td>Syncs your files across multiple devices but doesn't store your files on the server.</td></tr><tr><td>Filebrowser</td><td>Simple file sharing app but doesn't sync your files.</td></tr></tbody></table>


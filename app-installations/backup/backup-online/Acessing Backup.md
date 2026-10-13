---
label: Restoring Backup
order: 950
icon: ../../../assets/counterclockwise-arrows.png
---

<style>
.my-text { color: #000; }
html.dark .my-text { color: #eee; }
</style>

<div class="my-text">

### ⬇️ Restoring Backup Setup

If you just want to download an old version of a file, you can access the Web UI and follow instructions in the next header. This part will setup backrest on your PC, so you're still able to access your backups even if your server does go down. 

1. For Windows, [Download BackrestSetup-x86_64](https://github.com/garethgeorge/backrest/releases) and install it. For Linux, click show All Assets. Sorry Mac users. 
2. Create an **instance** and **user** the same way as before. 
3. Click **Add Repo** and give it a name that represents the server.
4. Under **Repository URI**, grab the endpoint link, and type this `s3:endpoint link/nameofyourbucket` (e.g. s3:s3.us-west-004.backblazeb2.com/chumbucket).
5. Enter the **password you generated before**, when you created the repository on the server.
6. Under **Env Vars**, click Add, name it `AWS_ACCESS_KEY_ID=` and paste the keyID. Click Add again, name this one `AWS_SECRET_ACCESS_KEY=` and paste the application key.
7. Click Test Configuration and hopefully it says connected. Click **Submit**.

### 🔄 How to Restore Backup 
1.	Click on your **Repository** -> **Index Snapshots**, this will update the snapshot list. Then under your username of your server, expand backup (or whatever you named your plan), expand the date, then you’ll see the snapshot. 
2.	On the right side, expand **Snapshot Browser**, and you'll see all the paths you added. You can download the entire folder or specifc files.


</div>



{% hint style="info" %}
[Accompanying video by AlienTech42](https://www.youtube.com/watch?v=ms4AnHgj9hc&t)
{% endhint %}
<style>
.my-text { color: #000; }
html.dark .my-text { color: #eee; }
</style>

<div class="my-text">

There you are, installing a bunch of cool containers, tweaking stuff, having a blast. Then you try something new and it breaks something, and can't get it back to normal. That is where Appdata Backup comes saves the day. Backing up your appdata and allowing you to restore it when somethings goes wrong.   

1. **Create a share** for the backups.
2. **Install** Appdata Backup by `Robin Kluth`.
3. Go to **Settings** →  **Backup/Restore Appdata** (under User Utilities).
4. For **Delete backups if older than x days** and **Keep at least this many backups**, it depends on how many changes and container installs you're doing. You can leave this at default if you're not sure. 
    - Keep in mind, these backups can get fairly big with media server metadata and game servers.
5. For **Backup destination** select the share you made in Step 1. Optionally enable multicore compression. 
6. Assuming you want to run this on a schedule, change **Scheduled Backup Frequency**. Again, the frequency depends on how many changes you're doing. In the beginning, you're still messing around a lot, so you can set it to run as often as daily, or use a custom schedule. The hour field uses a 24-hour format (e.g. 23 = 11 PM). 
7. Optionally, you can have **containers automatically update** after a backup. I personally like to update my containers manually, as updates can break things unexpectedly. 
8. In **container settings**, you can skip backing up a container and its appdata. You can also click on the container name to see more settings, allowing you to even skip a specific folder. If you have a mutli-mapping error, you would fix it here. On the right, you can also change the Start order if you want. 
9. Scroll down, and you can click on **manual backup** to make one right away. 

</div>

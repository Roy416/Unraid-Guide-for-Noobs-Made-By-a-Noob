# 📦 Mover

One of the **perks of having a cache drive** is that you can set it up so when you transfer files to your server, it will use the faster SSD speeds. Then later at night, those files would be transferred to the array. This is possible by the **mover feature**.

To set this up, click on a share to open its settings, and change primary storage to cache, and secondary storage to array. To change the time the mover occurs, go to Settings → Scheduler.

**Quiet your server** - Currently all the random stuff the server does occurs on the array, and when this happens the HDD makes noise. You can put all that on the cache drive to avoid that noise. For the appdata, domains, isos, and system shares, set the primary storage to cache, secondary storage to array, and set the mover action to array → cache. Then go to the main page and click move. Once that’s done, you can change the secondary storage of those drives to none.

**Stop the mover** - If you started the mover and it’s taking too long and want to stop it, go to the terminal and type **`mover stop`**. It might take some time for the mover to fully stop as it might be transferring the file it was currently moving.

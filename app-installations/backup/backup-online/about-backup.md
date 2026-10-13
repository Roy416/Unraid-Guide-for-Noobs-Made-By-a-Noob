<style>
.my-text { color: #000; }
html.dark .my-text { color: #eee; }
</style>

<div class="my-text">

You're probably thinking you should look into backing up your stuff because you either feel pressured by others yelling "3-2-1 STRATEGY OR DIE" or fear that your house might burn down and you'll lose all your precious photos and documents. There are a bunch of different ways to back up your data. I'll be showing you how to do it with **Backblaze** and **Backrest**.

### ❓ What is Backblaze
Backblaze is a **S3 compatible storage**. It's a lot cheaper than the typical cloud services you know. I pay $3.50 USD for 500gb and the typical cloud services have a minimum price of $10 per month (for a minimum plan of 2 TB).

"Why is S3 compatible storage so cheap?", you may ask. That's because it has **no fancy features** such as mobile apps, file sharing, or galleries, and it uses a **pay-as-you-go model**. For Backblaze, downloading all your files is essentially free. You will only have to start paying if you download more than 3x your storage size in a month. This works out great as we’re only using it to restore in case of emergencies.

### ❓ What is Backrest
After testing a few alternatives, I decided to use the backup software called Backrest. It’s based on **Restic** which is a super popular solution. Backrest encrypts your data, which is awesome for privacy. But it also means that if you open Backblaze, you'll only see encrypted files. So we will need to set up Backrest on your computer to decrypt and view your data. If you don't want your data encrypted, you can look at a solution such as rclone. 

These backups work differently than you might expect; it has some really smart features. Some of which include snapshots, deduplication and incremental backups. TLDR:

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f511">📝</span> TLDR</summary>

- You upload your data and a snapshot (**backup**) is created.
- If the data remains unchanged, then it doesn’t get uploaded twice (**deduplication**).
- If you edit a file, it’ll only change parts of that file and creates a new version (**incremental backups**) while keeping the old.  
- So if you create a new snapshot, it will have the newly edited file while the older snapshot will have the original file. 
- Extra info: A snapshot isn’t exactly a typical backup. All your files, old versions and new, are in one folder. When you restore a snapshot, it picks the files and their versions from that folder from when the snapshot was taken. 

</details>

</div>

<style>
.my-text { color: #000; }
html.dark .my-text { color: #eee; }
</style>

<div class="my-text">

### ⬇️ Installing Backrest

1.	**Create a free B2 Cloud Storage account** on Backblaze. Add your payment method, so that uploads won't fail when your storage is more than the free 10gb.
2.	Go to **Buckets** -> **Create a Bucket**. The name must be unique. Make note of the endpoint.
3.	Go to **Application Keys** -> **Add a New Application Key**. Put the keyID and applicationKey in a password manager, as you will need it later to retrieve your files.
4. **Install Backrest** by `AlexRed`. For **Path to backup** select the folder you want to back up. Click **Apply**.  
    - If there are files in another share you want to back up, scroll down, click Add another Path, Variable, Local Device, -> Give it a name, set a container path (e.g. /documents), and set the host path (e.g. /mnt/user/documents).  
    - You can also edit the Path to Backup's container path, so you can change `/backup` and give it a more descriptive name. 
5.	Open **Backrest's Web UI**. Name the Instance ID and create a user and password. 
6.	Click **Add Repo** and give it a name that represents the server.
7.	Under **Repository URI**, grab the endpoint link from Step 3, and type this `s3:endpoint link/nameofyourbucket` (e.g. s3:s3.us-west-004.backblazeb2.com/chumbucket).
8.	Type or Generate a **password**. You will **need this password to decrypt** your data later.  
9.	Under **Env Vars**, click Add, name it `AWS_ACCESS_KEY_ID=` and paste the keyID. Click Add again, name this one `AWS_SECRET_ACCESS_KEY=` and paste the application key. 
10.	Click **Test Configuration** and hopefully it says connected. Click **Submit**.

### 🗓️ Creating a Backup Schedule 
1.	Click **Add Plan**. Give it a **name** and select the **repository** that you just created. 
2. Under **scope** add `/backup` (or whatever you changed it to), and any other container paths you added.
5.	Next you can set up **how often you want a backup** to occur. Cron is a super flexible scheduler. You can use [this site](http://www.cronmaker.com/) to create your schedule. For example, if you want to back up every day at 6 AM, you'd enter `0 6 * * *`. 
6.	The **retention policy** decides how long it’ll keep a snapshot before it’s deleted. By default, it keeps one snapshot per day for the past 30 days, and one per month for the past 12 months. It’ll basically only be clearing up space (pruning) from the files you already deleted and old versions of files. If you want it to keep everything including deleted files and old versions of files, you can choose None, however your storage will be forever increasing. You can change the policy if it's not to your liking and Click **Submit**.
7. On the left, click on the plan you just created, and click **Backup Now**. 

</div>

# ⬇️ Installation

{% hint style="info" %}
[Immich's guide for Unraid](https://immich.app/docs/install/unraid/)
{% endhint %}

This is going to be a different kind of installation. Instead of installing Immich from the Community Apps, we will be using Docker Compose which is the official and recommended way. With the Immich template on the Community Apps, I remember you had to keep track of the version of the database before updating which I couldn't be bothered to do.&#x20;

1. **Create a share** for your photos and **create a folder** in the appdata share for Immich's database, PostgreSQL.&#x20;
2. **Go to Docker**, scroll all the way down, click **Add New Stack**, and give it a name.&#x20;
3. Go to [Immich's site](https://immich.app/docs/install/unraid) and download Immich Docker Compose from Step 4 and Immich Example.env in Step 7.
4. Click on the **Cog** next to the Stack you created, then **click Edit Stack -> click Compose File**. Delete whatever is there and paste the contents of the Docker Compose file you downloaded.
5. Edit the stack again and click Env file this time and copy and paste the content from Immich Example.env.
6. For `UPLOAD_LOCATION`  set it to the share you created for your photos (e.g. /mnt/user/photos). For `DB_DATA_LOCATION` set it to the folder you created for its database in the appdata share (e.g. /mnt/user/appdata/postgres).&#x20;
7. To set your timezone, remove the hashtag next to `TZ=Etc/UTC` and follow the link to the comment above it to find your timezone identifier. Click Save Changes.&#x20;
8. To the right of your stack, click Compose Up. It will start installing Immich. **DO NOT CLICK DONE** until it says connection closed.&#x20;
9. Once it says connection closed, you can go ahead and click done, and you'll see a bunch of containers appear. You won't be able to right click on it to go to the web ui, but next to immich\_server it'll say the port for immich, which is 2283. So you can access immich with IP:2283.&#x20;
10. From here it's pretty straight forward. Last I checked, the default storage template was kind of unusable. I use this  `{{#if album}}{{album}}/{{filename}}{{else}}{{y}}/{{MM}} - {{MMM}}/{{filename}}{{/if}}` , so if a photo is in an album, it'll be in that album's folder, and if its not in an album then itll be in the folder of its year, within a folder of the month. You can change this anytime within the admin settings.&#x20;


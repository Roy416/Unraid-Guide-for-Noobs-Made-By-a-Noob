# 🔒 Share Permissions

{% hint style="info" %}
[Accompanying video by TechnGo](https://www.youtube.com/watch?v=PePFc-eQCsY)
{% endhint %}

## Creating Users

Currently you have a root user, however you wouldn't want to give that to just anyone or have that on your laptop for example. So you can create users with certain restrictions.&#x20;

1. Go to the **Users** tab
2. Click **Add User**
3. Fill in your **name** and **password** and click **Add**

Click on the share you created and you will see a new section called **SMB Security Settings**. The two settings we're concerned with are **Export** and **Security**.&#x20;

&#x20;The export settings dictate how the share appears under the Network section in file explorer on your computer.&#x20;

<table><thead><tr><th width="219">Export Options</th><th>Descriptions</th></tr></thead><tbody><tr><td><strong>No</strong></td><td>Cannot access the share</td></tr><tr><td><strong>Yes</strong></td><td>Can access the share</td></tr><tr><td><strong>Yes (hidden)</strong> </td><td>Can't visually see the share, but can still access it</td></tr><tr><td>Time Machine</td><td>This refers to the back up feature on Mac OS and if it can see the share</td></tr></tbody></table>

Security controls who can read and write to the share.&#x20;

<table><thead><tr><th width="222">Security Options</th><th>Descriptions</th></tr></thead><tbody><tr><td><strong>Public</strong></td><td>Anyone on the network can read and write </td></tr><tr><td><strong>Secure</strong></td><td>Anyone can read, select users can write</td></tr><tr><td><strong>Private</strong> </td><td>Can choose select users who can read or write</td></tr></tbody></table>


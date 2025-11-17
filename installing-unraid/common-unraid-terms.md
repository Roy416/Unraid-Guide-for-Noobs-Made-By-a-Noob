# 📖 Common Unraid Terms

### A**rray**

An array is where your hard drives live. You can think of it of as linking all your drives together creating one gigantic storage space. But unlike traditional RAID, you're still able to go into each hard drive and see what files are on there. Also unlike RAID, if one of your storage drive dies, only the data on that drive would be jeopardized, not all the data on the array.&#x20;

You also don't need to have an array. Which is nice for if you want to make a full SSD build.&#x20;

### **Parity Drives**

Parity parity parity, you must have heard this term a bunch of times when watching videos about Unraid. Similar to a backup drive, a parity drive serves to prevent data loss, but THEY ARE NOT THE SAME.&#x20;

What a parity drive does is it keeps track of all the data that is being written to your array and waits for one of your storage drives to fail. If a storage drive does fail, then the parity drive swoops in and saves that data.

However, there is **no guarantee the the parity drive will be successful in retrieving your lost data**, whereas a backup already has a copy of it. The positive about the parity drive is that you just need one drive to cover the failure of the rest of your drives, whereas you would need multiple backup drives to duplicate your data. If two of your drives die at once and you only have one parity drive, then gg no re (you're shit out of luck).&#x20;

Another thing to note is that a **parity drive won’t be counted as your storage space**. The parity drive’s storage must also be either equal or larger than your storage drives. This makes sense because if you have a 4TB parity drive, but one of your 8TB storage drives fails, it wouldn’t be able to save all 8TB of data.

There is also **one dumb thing about parity drives**. If one of your drives dies, and the parity drive starts doing the recovery process, during that process is the highest chance that the parity drive will die. So to mitigate that, you need a second parity drive..

### Cache Pools

Cache pools are just a group of SSDs. They work more like traditional RAID. There are even some configurations with parity but it isn't quite the same as parity drives in arrays. More info on this in the following sections. You can also create multiple pools for different purposes.&#x20;

It's recommended to have a SSD to put the app data folder and other system folders on it, making the **server** **more responsive** and **reducing HDD noise**.

Unraid also has a cool feature called **Mover**. Where files are initially downloaded to the SSD making use of its speed, then later at night those files are moved to the Array.&#x20;

In terms of file transfer speeds, having a nice SSD isn't enough. You'd have to upgrade your network hardware of your server and PC to take advantage of those 10 GbE speeds. Which include having a 10 GbE Network Interface Card on both your server and PC, and 10 GbE switch to connect to two (or you can bypass the switch and just have two connected by a cable. MOVE THIS TO HARDWARE?\
\
An SSD cache in Unraid won’t give you faster transfers over the network unless your **network hardware** can keep up.



have some of the stuff below in choosing hardware?

* By using an **SSD as a cache drive**, you can put the app data folder and other system folders on it, making your **server** **more responsive** and **reducing HDD noise**.
* By using an **SSD as a cache drive**, you can _potentially_ take advantage of its speed to **increase the file transfer speed**. I say potentially because you’re going to need more gear to take advantage of that speed, such as a switch, 10 gigabit network card, etc.
* Positives aside, **a cache drive is also somewhat of a** **common point of failure**. Causing you to lose whatever personal files were on the drive at that time and losing your app data, so you would have to set up your apps from scratch again.
* To combat this, you could firstly backup your app data (shown later). So if something does happen, you can easily load it back in. Another solution is to get another cache drive, where Unraid automatically makes one of the drives mirror the data of the other cache drive (aka raid1).

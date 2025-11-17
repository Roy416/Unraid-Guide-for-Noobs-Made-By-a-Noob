# 🖥️ Booting into Unraid

{% hint style="info" %}
[Accompanying video by Elevated Systems](https://youtu.be/huCE4jtXOjQ?si=ntawSW9K5kuVdIj4\&t=180)
{% endhint %}

Now that you've created your USB Installer, plug it into a usb 2.0 port on your server. Before we can boot into Unraid, there are some settings we need to set in the bios. For this you will need to connect a monitor and keyboard to your server.&#x20;

### ⚙️ Bios Settings

1. Restart your server and enter the bios settings. The key to enter it is usually DEL,  but it will say at the bottom of the screen.
2. Locate where to change the **Boot Priority**, and move the Unraid USB to the first slot. &#x20;
3. If you're interested in **Virtual Machines**, you will need to turn on a setting. These can have different names, but look for SVM Mode and IOMMU, or Intel (VMX) Virtualization Technology. &#x20;
4. Save the changes and reboot, and you should be greeted with Unraid's menu.&#x20;
5. Press Enter to select the first option and Unraid will start booting up. After some time it will ask you to login and above it will say the **IPv4 address**. Note this down as this is the address dedicated to your Unraid Server and is how you can access it from any other computer on the network.&#x20;

### 👢 Can't boot into Unraid?

If you changed your boot priority and it’s still not booting into Unraid, go into your bios and look for a “fast boot” or “secure boot” option in the boot settings. Disable it and hopefully you’re booted into Unraid (had this issue with a Dell Optiplex).

# 💾 Unraid USB Creator

{% hint style="info" %}
[Accompanying video by Elevated Systems](https://www.youtube.com/watch?v=huCE4jtXOjQ)
{% endhint %}

### 💾 Choosing a USB

The Unraid OS runs off of your USB instead of it being installed on one of your drives. The one **requirement of the USB** is it needs to have a **GUID**. This is how Unraid links your license to the USB.

You might ask, **“How do I know which USBs have a GUID?”.** For me, I checked amazon reviews to see if it worked with Unraid. Or you can use a USB you’ve seen other installation guides use. Personally, I bought [this](https://www.amazon.ca/dp/B015CH1JIW?ref=ppx_yo2ov_dt_b_product_details\&th=1). USBs with the "fit" moniker are also popular for their small size.&#x20;

Unraid recommends using a **USB with** **32GB or less** and supposedly **plugging it in a 2.0 port** **is also** **more reliable**.

### 🛠️ Creating the USB Installer

1. Go to [Unraid's download page](https://unraid.net/download), download the installer for your OS, and install it.&#x20;
2. Choose the **recommended version** for the OS and your **USB stick**. If it doesn't show the options for either of the two, close the program and try again.&#x20;
3. Type the **name** of your server and select **DHCP** as the network mode, and click continue.&#x20;

### ⚠️ Incompatible USB?

When trying to create the Unraid USB, you might get an incompatible error like I did. If you do, you can follow [Unraid’s Instructions](https://docs.unraid.net/unraid-os/manual/getting-started/manual-install-method/) on how to create it manually.

You also want to change the “EFI” directory to “EFI-“ so you can use the bios menu (UEFI) that comes with your motherboard.

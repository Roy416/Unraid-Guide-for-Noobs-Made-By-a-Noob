# ⬇️ Installation

{% hint style="info" %}
[Accompanying video by Spaceinavder](https://www.youtube.com/watch?v=U47nvwXrAOo\&t)
{% endhint %}

{% embed url="https://docs.google.com/presentation/d/1O-A-cddHNqX6XmLPVWJOtMZWA7Zexgg1FrmVJQIECic/edit?usp=sharing" %}

1. **Create a share** named `nextcloud`. This is where your files will reside as well as Nextcloud's appdata. &#x20;
2. Go to **Settings -> Docker**, click on the toggle on the top right to show the **Advanced View**,  set **Enable Docker** to `No` and click Apply. Then set **Preserve user defined networks** to `Yes`, and set **Enable Docker** to `Yes` again and click Apply.&#x20;
3. Click on Apps and **install the official container of Nextcloud AIO**.
4. Go to its **Web UI**, and you'll be greeted with a Warning screen. **Click Advanced** and **click Accept the Risk and Continue**.&#x20;
5. You'll be shown a pass phrase, which is a recovery key. **Take note of the pass phrase** in a password manager of sorts as this is the only time you'll see it. Click **Open Nextcloud AIO login and paste the pass phrase.**
6. If you bought a domain, follow the instructions of giving access of the method you chose. Set the scheme to http, the port to 11000, and the IP to just your server's IP (I couldn't get it work with a container name).&#x20;
7. Enter your **domain** and click **Submit Domain**.
8. **Choose the optional containers** interest you, and **click Save changes**. These can be enabled/disabled later under the App settings (I'm not sure if Collabora can be enabled after installation though). Scroll down and **change your timezone** and **click submit timezone**, and **click Download and start containers**. This will take a minute.
9. You'll get a screen with the status of the containers, **after a moment click** **Reload** and they should all be running.&#x20;
10. When they're all running, your **initial username and password** will show. Click **Open your Nextcloud**, and **use that info to login**.&#x20;

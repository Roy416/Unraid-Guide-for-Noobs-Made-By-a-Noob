# 🛠️ Further Tinkering

## 🚗 Array auto start

* By default, when you turn on your sever, the array does not automatically start.
* To change this, go to **Setting -> Disk Settings**, and change **Enable auto start** to **Yes**.&#x20;

## 💿 Spin down

* Unraid has a feature called **spin down** where you can essentially **turn off your drives after a certain amount of time of them not being in use**, thus reducing noise, heat, and power consumption. Then the drive turns back on once something needs to access the files on it. This does create some loading time, for example a movie would take 5-10 seconds extra to load.
* There is some debate on whether you should do this as some claim the action of the drive starting up really stresses it. But it seems the general consensus is that spinning down your drives is fine and any reduction of life span of your drive is negligible. However, if your server’s in a cold environment (e.g. a garage during winter), spinning down the drive will decrease its life span as the drive has to start up from a cold temperature.
* By default, spin down delay is disabled. To change the default spin delay, go to **Settings → Disk Settings → Default spin down delay**. To change it per drive, click on a drive’s name and you’ll see the setting for “spin down delay”.&#x20;

## ✔️ Parity Check

* A parity check checks if the parity’s data is still consistent with the files on the array drives. Running this every 3 months seems to be the general consensus.
* If a discrepancy is detected, it will let you know. However, it will not fix it or tell you where the file is exactly located. In the off chance it does happen you can look at the error it logs and investigate it.
* There is an option to “write corrections to parity”, **you do not want this**. As this leaves you in the dark on what file is corrupt. **how to set parity ysettings**&#x20;

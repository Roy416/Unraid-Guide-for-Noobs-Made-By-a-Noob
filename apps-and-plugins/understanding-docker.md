# ⛴️ Understanding Docker

### :question: What is **Docker?**

Docker is a platform that allows you to run apps. These apps are isolated in their own “containers” or environment, so they don’t interfere with each other. Here are some other terms you'll come across:

**Image** - Essentially the download file for the app

**Volume** - Assigning storage space for the app

**Docker Compose** - Docker Compose is like a pre-made configuration file, where it’ll have the settings. It also gets the image, and sets up all the volumes and stuff, so you don’t need to do a thing (other than put your system’s info). Some services don’t have a sample docker compose file but other people may have posted theirs for you to use.

### :disguised\_face: Unraid is Linux..?

Under the hood, Unraid is indeed running a custom version of Linux. So when you're poking around your files or messing around with containers, you might see /var, /opt, and /mnt, which are Linux's filesystem directories. This also means that each docker container is running in its own Linux environment.&#x20;

### :vs: Community Apps vs Docker Compose

Since Unraid is Linux, that means a typical Docker Compose configuration can also be used. Some people even prefer using Docker Compose to install services directly from the source (seen as Compose on the Docker tab). It does require you to understand the configuration file and how to put your own settings in, but it is generally straight forward after a little learning. With that being said, I personally still install from the Community Apps since it's more convenient :woman\_shrugging:.&#x20;

### :performing\_arts: Different Versions?

When you look for an app on Community Apps, you might see multiple versions. All those different versions are different "docker templates". A docker template in the context of Unraid, is basically everything a docker compose file has but it's tailored for Unraid. And different maintainers created their own templates which is why different versions appear. The version of the app may even differ. &#x20;

Some recommended templates are by hotio or linuxserver, otherwise I get whichever one was updated most recently.&#x20;

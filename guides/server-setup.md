How to Setup a Server
=====================

1. **Create a droplet on DigitalOcean.** In general, opt for Ubuntu 12.04 64-bit. Make sure to
   enable Private Networking and Backups.

1. **Create a user and disable `root` login.**

   1. ssh into  `root` and create a user by running `adduser` and filling out the fields. On
      production machines, name the user `labs`.
   1. Give them sudo privileges with `usermod -aG sudo <username>`.
   1. Disable root login by editing `/etc/ssh/sshd_config` and setting `PermitRootLogin` to `no`.
   1. Restart SSH for the change to take effect: `service ssh restart`.

1. **Log in and create a `README` in the home directory.** Make sure to include:

   - What the server is being used for
   - Any running processes on the server (e.g., Apache, MySQL, Redis, etc.)
   - The public and private IP address (found in the "Settings" tab of the droplet on DigitalOcean
   - Any special notes about how the server is configured

1. **Update installed software.**

   ```bash
   $ sudo apt-get update
   $ sudo apt-get upgrade
   ```

   Note that you may want to restart after this `sudo shutdown -r 0`.

1. **Set the Fully Qualified Domain name.** I don't know why this is important but anything with
   Apache complains if you don't have it. See instructions [here](https://library.linode.com/getting-started#sph_update-etc-hosts).

1. **You're done!** If you want to go on setting up a particular platform, check out some of these
   guides:

   - [LAMP: Linux, Apache, MySQL, PHP](https://www.digitalocean.com/community/articles/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu) (note that for many projects, we only need Apache
     and will use our dedicated MySQL server.

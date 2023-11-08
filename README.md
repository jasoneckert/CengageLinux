# CengageLinux
Updates for ***Linux+ and LPIC-1 Guide to Linux Certification (6th Edition)***, ISBN: 9798214000800

In this book, you install virtual machines of the latest Fedora Workstation and Ubuntu Server for your architecture (x86_64 or aarch64) on a Windows or macOS system.

New versions of each Linux distribution are released frequently. While nearly all steps within the hands-on projects and discovery exercises in this book will remain the same for newer versions of Linux, there may be some steps that need to be modified. You can find these steps for each new version of Fedora Workstation and Ubuntu Server in this repository. You will also find any miscellaneous changes that related to new versions of Windows or macOS.

## Changes for Fedora Workstation 39 (x86_64 or aarch64) 
- ***Project 2-1 Step 4 (pg 66)*** - Click *Install Fedora* to start the Fedora installation.
- ***Project 2-1 Step 11 (pg 66)*** - Note that the *Power Off/Log Out* drop-down menu has been replaced with a graphical power icon.
- ***Project 2-2 Step 5 (pg 67)*** - Note that the login screen on tty1 is displayed as *seat0* in the output of `who`.
- ***Project 2-3 Step 2 (pg 68)*** - The *Show Applications* icon is now called *Show Apps*.
- ***Project 2-6 Step 5 (pg 70)*** - When you run `info`, you will be prompted to press `y` (twice) to install the info utility, as it is no longer installed by default. 
- ***Project 5-2 Step 4 (pg 207)*** - The first command run in this step should be `df -hT`. 
- ***Project 5-4 Step 4 (pg 209)*** - `mkpart` first prompts you to supply a partition name. Press Enter to choose a blank name.
- ***Project 5-4 Step 11 (pg 210)*** - The first command run in this step should be `vgcreate vg00 device`, where *device* is the device file for the 1GB partition created in Step 4.
- ***Project 5-6 Step 9 (pg 212)*** - Fedora now converts entries in /etc/fstab to Systemd mount units (discussed later in Chapter 8), but this conversion is performed only during system startup. After executing the `mount` command in this step run the `systemctl daemon-reload` command to complete this conversion. 
- ***Project 6-6 Step 3 (pg 255)*** - Click *Not Now* to continue to use the live Fedora system.
- ***Project 8-2 Steps 6-8 (pg 357)*** - Fedora no longer ships with any UNIX SysV daemons, such as livesys. Consequently, `chkconfig` is no longer installed to manage them. 
- ***Project 8-2 Step 20 (pg 357)*** - Since livesys is no longer available, instead run `service crond restart` and note that legacy `service` command functionality is now handled by Systemd. 
- ***Project 8-3 Step 4 (pg 358)*** - The first line of the bootscript.service file should read `[Unit]`. 
- ***Project 9-5 Steps 8 and 9 (pg 388)*** - The `crontab` command now opens `nano` instead of `vi` by default. 
- ***Project 11-8 Step 2 (pg 481)*** - This step is no longer necessary as flathub is now added and enabled by default. 
- ***Project 11-8 Steps 3-7 (pg 481)*** - Replace *Teams* with *Edge* to install, view, and run Microsoft Edge. 
- ***Project 12-4 Step 4 (pg 523)*** - When you run `telnet`, you will be prompted to press `y` (twice) to install the telnet utility, as it is no longer installed by default. 
- ***Project 13-4 Step 2 (pg 570)*** - This step is no longer necessary as httpd is now installed by default. 
- ***Discovery Exercise 13-4 (pg 581)*** - Because sshfs is now installed by default, there is no need to run `dnf install sshfs`. 

## Changes for Ubuntu Server 23.04 (x86_64 or aarch64) 
- ***Project 10-3 Step 2 (pg 424)*** - This step is no longer necessary as rsyslog is now installed by default. 
- ***NetPlan .yaml syntax (pg 494)*** - While the syntax displayed in the sample `00-installer-config.yaml` file will work fine, the `gateway4: 3.0.0.1` line now uses a deprecated syntax. The preferred syntax for setting this default gateway is now:
  ```
  routes:
    - to: default
      via: 3.0.0.1
  ``` 
- ***Project 13-3 Step 3 (pg 570)*** - NTP daemon configuration is now stored in /etc/ntpsec/ntp.conf. Consequently, you must run the `less /etc/ntpsec/ntp.conf` command in this step. 

## Miscellaneous Changes 
- ***Discovery Exercise 12-4 (pg 528)*** - On Windows, `wsl` no longer assumes a default distribution of Ubuntu. As a result, you must run the `wsl --install --distribution ubuntu` command to install Ubuntu WSL. 

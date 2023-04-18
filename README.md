# CengageLinux
Updates for ***Linux+ and LPIC-1 Guide to Linux Certification (6th Edition)***, ISBN: 9798214000800

In this book, you install virtual machines of the latest Fedora Workstation and Ubuntu Server for your architecture (x86_64 or aarch64) on a Windows or macOS system.

New versions of each Linux distribution are released frequently. While nearly all steps within the hands-on projects and discovery exercises in this book will remain the same for newer versions of Linux, there may be some steps that need to be modified. You can find these steps for each new version of Fedora Workstation and Ubuntu Server in this repository. You will also find any miscellaneous changes that related to new versions of Windows or macOS.

## Changes for Fedora Workstation 38 (x86_64 or aarch64) 
- ***Project 2-1 Step 4 (pg 66)*** - Click *Install Fedora* to start the Fedora installation.
- ***Project 2-3 Step 2 (pg 68)*** - The *Show Applications* icon is now called *Show Apps*.
- ***Project 2-6 Step 5 (pg 70)*** - When you run the `info` command, you will first be prompted to press `y` (twice) to install the info utility, as it is no longer installed by default. 
- ***Project 5-2 Step 4 (pg 207)*** - The first command run in this step should be `df -hT`. 
- ***Project 5-4 Step 4 (pg 209)*** - After running `mkpart`, you are first prompted to supply a partition name. Press Enter to choose a blank name.
- ***Project 6-6 Step 3 (pg 255)*** - Click *Not Now* to continue to use the live Fedora system.
- ***Project 8-2 Steps 6-8 (pg 357)*** - Fedora no longer ships with any UNIX SysV daemons, such as livesys. Consequently, the `chkconfig` command is no longer installed to manage them. 
- ***Project 8-2 Step 20 (pg 357)*** - Since livesys is no longer available, instead run `service crond restart` and note that legacy `service` command functionality is now handled by Systemd. 
- ***Project 8-3 Step 4 (pg 358)*** - The first line of the bootscript.service file should read `[Unit]`. 
- ***Project 9-5 Steps 8 and 9 (pg 388)*** - The `crontab` command now opens the `nano` editor instead of `vi` by default. 
- ***Project 11-8 Step 2 (pg 481)*** - This step is no longer necessary as flathub is now added and enabled by default in Fedora. 
- ***Project 11-8 Steps 3-7 (pg 481)*** - Replace *Teams* with *Edge* to install, view, and run Microsoft Edge. 
- ***Project 12-4 Step 4 (pg 523)*** - When you run the `telnet` command, you will first be prompted to press `y` to install the telnet utility, as it is no longer installed by default. 
- ***Project 13-4 Step 2 (pg 570)*** - This step is no longer necessary as httpd is now installed by default in Fedora. 
- ***Discovery Exercise 13-4 (pg 581)*** - There is no need to run the `dnf install sshfs` command as sshfs is now installed by default in Fedora. 

## Changes for Ubuntu Server 23.04 (x86_64 or aarch64) - COMING APRIL 20, 2023

## Miscellaneous Changes 
- ***Discovery Exercise 12-4 (pg 528)*** - On Windows 10 and later, a default distribution is no longer chosen by the `wsl` command. As a result, you must run the `wsl --install --distribution ubuntu` command to install Ubuntu. 

# Updates for ***Linux+ and LPIC-1 Guide to Linux Certification***

In this book, you install virtual machines of the latest Fedora Workstation and Ubuntu Server for your architecture (x86_64 or aarch64) on a Windows or macOS system.

New versions of each Linux distribution are released frequently. While nearly all steps within the hands-on projects and discovery exercises in this book will remain the same for newer versions of Linux, there may be some steps that need to be modified. You can find these steps for each new version of Fedora Workstation and Ubuntu Server in this repository. You will also find any miscellaneous changes that related to new versions of Windows or macOS, as well as any typos noticed following publication.

Step modifications are posted below for the following two (2) editions of the book:
- 6th Edition, ISBN: 9798214000800 and 9798214000947
- 7th Edition, ISBN: 9798214409962

# 7th Edition, ISBN: 9798214409962

## No changes currently

# 6th Edition, ISBN: 9798214000800 and 9798214000947

## Changes for Fedora Workstation 42 (x86_64 or aarch64) 
- ***Project 2-1 Step 4-15 (pg 66-67)*** - Fedora 42 now uses an entirely new installer. Replace Step 4 onwards with the following:
  - After the graphical desktop and Welcome to Fedora screen have loaded, select ***Install Fedora*** to start the Fedora installation program.
  - At the Welcome screen, select ***English (United States)*** and click ***Next***.
  - On the Installation method screen, note that your 50 GB virtual disk is called sda and that the entire disk will be used to install Fedora. Select ***Launch storage editor*** from the ellipsis (three-dot) menu in the upper-right section of the window and click ***Launch storage editor*** to edit the storage configuration manually.
    - Select ***Create partition table*** from the ellipsis menu next to sda. Note that GPT is selected by default and click ***Initialize***. After the GPT has been created, Free space will be listed under sda and be available for creating partitions.
    - Select ***Create partition*** from the ellipsis menu next to Free space. Supply the following information and click ***Create***. If your hypervisor provides a UEFI BIOS, supply the following information and click ***Create***. Otherwise, skip this step.
      - Name = UEFI
      - Mount point = /boot/efi
      - Type = EFI System Partition
      - Size = 1 GB
    - Select ***Create partition*** from the ellipsis menu next to Free space. Supply the following information and click ***Create***.
      - Name = Boot Partition
      - Mount point = /boot
      - Type = EXT4
      - Size = 1 GB
    - Select ***Create partition*** from the ellipsis menu next to Free space. Supply the following information and click ***Create***.
      - Name = Root Partition
      - Mount point = /
      - Type = EXT4
      - Size = 35 GB
    - Note the additional unpartitioned Free space on your first disk for a later exercise and click ***Return to installation***. 
    -	Click ***Continue*** to return to the Installation method screen. Note that your storage configuration is selected and click ***Next***.
  - On the Review and install screen, click ***Install***.
  - When the installation has finished, click ***Exit*** to live desktop to return to your Fedora live desktop.
  - Click the icon area in the upper-right corner of the Fedora live desktop, click the power symbol icon on the far-right side, and select ***Power Off***. Click ***Power Off*** to shut down your Fedora Live installation image.
  - In the Settings for the virtual machine in your virtualization software, ensure that the virtual DVD drive is no longer attached to the live media ISO image of Fedora Workstation Linux.
  - Start your Fedora Linux virtual machine using the virtualization software to boot into your new operating system.
  - At the Welcome screen of the Setup wizard, ensure that English is selected and click ***Next***. 
    - At the Typing page, ensure that an English (US) keyboard is selected and click ***Next***.
    - At the Privacy page, disable Location Services and Automatic Problem Reporting using the sliders and click ***Next***. 
    - At the Time Zone page, select your nearest city by locating it on the map or entering its name into the search box. Verify that the correct time zone and time are listed and click ***Next***.
    - At the Third-Party Repositories page, click ***Enable Third-Party Repositories*** and click ***Next***.
    - On the About You page, supply your full name in the Full Name text box, enter `user1` in the Username text box, and then click ***Next***. 
    - At the Password page, supply a password of `LINUXrocks!` in both text boxes. Click ***Next*** and then click ***Start Using Fedora Linux***.
  - At the Welcome to Fedora Linux Wizard, click ***Take Tour***. Navigate through the wizard using the arrow icons and close the window when finished.

- ***Project 2-2 Step 5 (pg 67)*** - Note that the login screen on tty1 is displayed as *seat0* in the output of `who`.
- ***Project 2-3 Step 2 (pg 68)*** - The *Show Applications* icon is now called *Show Apps*.
- ***Project 2-3 Step 6 (pg 68)*** - The latest version of `dnf` (dnf5) no longer uses the `groupinstall` argument. You must instead run the `dnf install @kde-desktop-environment` command to install KDE Plasma Workspaces.
- ***Project 2-3 Step 7 (pg 68)*** - Fedora no longer ships with X.org (X11). When you click the Plasma option from the GDM screen, you will start KDE Plasma Workspaces on Wayland, and a component called XWayland will emulate X.org for any apps that require X.org.
- ***Project 2-3 Step 10 (pg 68)*** - To open a new tab, you now click the New Terminal icon in the upper left corner of the app.
- ***Project 2-6 Step 5 (pg 70)*** - When you run `info`, you will be prompted to press `y` (twice) to install the info utility, as it is no longer installed by default. 
- ***Project 5-2 Step 4 (pg 207)*** - The first command run in this step should be `df -hT`. 
- ***Project 5-4 Step 4 (pg 209)*** - `mkpart` first prompts you to supply a partition name. Press Enter to choose a blank name.
- ***Project 5-4 Step 11 (pg 210)*** - The first command run in this step should be `vgcreate vg00 device`, where *device* is the device file for the 1GB partition created in Step 4.
- ***Project 5-6 Step 9 (pg 212)*** - Fedora now converts entries in /etc/fstab to Systemd mount units (discussed later in Chapter 8), but this conversion is performed only during system startup. After executing the `mount` command in this step run the `systemctl daemon-reload` command to complete this conversion. 
- ***Project 6-6 Step 3 (pg 255)*** - Click *Not Now* to continue to use the live Fedora system.
- ***Project 7-5 Step 12 (pg 316)*** - Ensure that you use backquotes (\`) instead of single quotes (\') around the values of the `FILE` and `DATE` variables (the compositor changed them before print).
- ***Project 8-1 Step 5 (pg 356)*** - Also ensure that you edit the `GRUB_DISABLE_SUBMENU=true` line to read `GRUB_DISABLE_SUBMENU=false` before saving your changes to /etc/default/grub. 
- ***Project 8-1 Step 7 (pg 356)*** - If you do not see the GRUB2 boot screen, just log into the system and reboot it again using `reboot` command. 
- ***Project 8-2 Steps 6-8 (pg 357)*** - Note that Fedora no longer ships with any UNIX SysV daemons, such as livesys. 
- ***Project 8-2 Step 20 (pg 357)*** - Note that while the livesys daemon is now Systemd-compatible, the `service` command functionality is still handled by Systemd. 
- ***Project 8-3 Step 4 (pg 358)*** - The first line of the bootscript.service file should read `[Unit]`.
- ***Project 8-4 Step 3 (pg 358)*** - The disk UUID is now the 4th column in the output of `lsblk --fs`, thus the proper command in this step is `:r !lsblk --fs |grep newmount|awk '{print $4}'`.
- ***Project 8-5 Steps 2-5 (pg 359)*** - X.org is no longer included in Fedora 41 and later, and the XWayland component is used to provide backwards compatibility for apps that require X.org. As a result, the `startx` command will not run in Fedora 42 and you can instead log into your GNOME desktop from the GDM as described in Step 6.
- ***Discovery Exercise 8-5 (pg 360)*** - Since the i3 window manager requires X.org, and X.org is no longer included in Fedora 41 and later, you can instead run the `dnf -y install sway` command to install the Sway window manager (the Wayland equivalent of i3).
- ***Project 9-4 Step 4 (pg 388)*** - To exit the help page in the `top` command, you must now press either `q` or `Esc` (as indicated on the screen). 
- ***Project 9-5 Steps 8 and 9 (pg 388)*** - The `crontab` command now opens `nano` instead of `vi` by default. 
- ***Project 10-4 Step 3 (pg 425)*** - The journald configuration file is now in a different location. Run `cat /usr/lib/systemd/journald.conf` in this step. 
- ***Project 11-4 Step 2 (pg 478)*** - The latest version of `dnf` (dnf5) no longer uses the `groupinstall` argument. You must instead run the `dnf install @development-tools` command to install the Development Tools group.
- ***Project 11-5 Step 10 (pg 479)*** - The latest version of `dnf` (dnf5) no longer requires the `available` argument. You must instead run the `dnf list | grep ncompress` command to view the available ncompress package.
- ***Project 11-8 Step 2 (pg 481)*** - This step is no longer necessary as flathub is now added and enabled by default. 
- ***Project 11-8 Steps 3-7 (pg 481)*** - Replace *Teams* with *Edge* to install, view, and run Microsoft Edge. 
- ***Project 12-4 Step 4 (pg 523)*** - When you run `telnet`, you will be prompted to press `y` (twice) to install the telnet client utility, as it is no longer installed by default. 
- ***Project 12-6 (pg 526)*** - TigerVNC runs on Wayland exclusively as a Systemd unit. After installing it in Step 2, log into a desktop environment as user1, run `vncserver`, specify your remote connection password (no view-only password) and note the first display number provided. You can then proceed to Step 6. In Step 8, you will supply `IP:5901` within the VNC Server dialog box to connect to the VNC server. Step 10 is unnecessary. 
- ***Project 13-4 Step 2 (pg 570)*** - This step is no longer necessary as httpd is now installed by default. 
- ***Discovery Exercise 13-4 (pg 581)*** - Because sshfs is now installed by default, there is no need to run `dnf install sshfs`. 

## Changes for Ubuntu Server 24.04 LTS (x86_64 or aarch64) 
- ***Project 10-3 Step 2 (pg 424)*** - This step is no longer necessary as rsyslog is now installed by default.
  
- ***NetPlan .yaml syntax (pg 494)*** - While the syntax displayed in the sample `00-installer-config.yaml` file will work fine, the `gateway4: 3.0.0.1` line now uses a deprecated syntax. The preferred syntax for setting this default gateway is now:
  ```
  routes:
    - to: default
      via: 3.0.0.1
  ``` 
- ***Project 12-1 Step 20 (pg 522)*** - Ubuntu now stores network configuration in /etc/netplan/50-cloud-init.yaml. Consequently, you must run the `cat /etc/netplan/50-cloud-init.yaml` command in this step. 

- ***Project 13-3 Step 3 (pg 570)*** - NTP daemon configuration is now stored in /etc/ntpsec/ntp.conf. Consequently, you must run the `less /etc/ntpsec/ntp.conf` command in this step. 

- ***Discovery Exercise 14-10 (pg 638)*** - In the `apt install` command, replace `sssdad` with `sssd-ad`. 

## Miscellaneous Changes 
- ***Discovery Exercise 12-4 (pg 528)*** - On Windows, `wsl` no longer assumes a default distribution of Ubuntu. As a result, you must run the `wsl --install --distribution ubuntu` command to install Ubuntu WSL. 

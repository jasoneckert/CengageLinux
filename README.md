# Updates for ***Linux+ and LPIC-1 Guide to Linux Certification***, 7th Edition

In this book, you install virtual machines of the latest Fedora Workstation and Ubuntu Server for your architecture (x86_64 or aarch64) on a Windows or macOS system.

New versions of each Linux distribution are released frequently. While nearly all steps within the hands-on projects and discovery exercises in this book will remain the same for newer versions of Linux, there may be some steps that need to be modified. You can find these steps for each new version of Fedora Workstation and Ubuntu Server in this repository. You will also find any miscellaneous changes that related to new versions of Windows or macOS, as well as any typos noticed following publication.

Step modifications are posted below for the ***7th edition*** of the book: ISBN 9798214409962 (print) and 9798214410029 (digital) 

## Changes for Fedora Workstation 45 (x86_64 or aarch64) 

- ***Project 2-1 Step 6 (pg 69)*** - To launch the storage editor, you now just click the ***"If none of the options above apply, use the storage editor..."*** link on the main page.
- ***Project 2-1 Step 12 (pg 69)*** - You are no longer required to choose your language and keyboard layout at the beginning of the Setup wizard (it uses the one you chose during the Fedora installation). Simply click ***Start Setup*** and you will progress to the Privacy page.
- ***Project 2-2 Step 5 (pg 70)*** - Starting with Fedora 45, you will no longer see local command-line terminals (e.g., `tty3`, `tty4`) in the output of the `who` command. Instead, Fedora now uses pseudo terminal sessions (`pts/0`, `pts/1`, and so on.) for local command-line terminals, and each `pts` entry will follow a `seat0` entry to denote that the user is seated at a local terminal.
- ***Project 2-3 Step 12 (pg 71)*** - In the latest KDE, you must click the ***Session*** option and choose ***Log Out***.
- ***Project 2-4 Steps 3, 4, 5, and 9 (pg 71-72)*** - Note that both `screen` and `tmux` leverage only a single pseudo terminal session in Fedora 45.
- ***Project 5-2 Steps 5 and 7 (pg 221)*** - `du -hT` should be `df -hT` in both of these steps.
- ***Project 8-1 Step 7 (pg 378)*** - If the GRUB boot screen doesn't appear automatically during boot, press Esc immediately after boot.
- ***Project 8-1 Step 12 (pg 379)*** - `runlevel` has been removed from Fedora 45. Instead, run `systemctl list-units --type=target` and note that the ***rescue.target*** is loaded and active.
- ***Project 8-2 Step 2 (pg 379)*** - Run `systemctl list-units --type=target` and note that the ***graphical.target*** is loaded and active.
- ***Project 8-2 Steps 5, 6, and 7 (pg 379)*** - You can skip these steps as Fedora 45 has removed backwards compatibility support for SysV init, including /etc/rc.d/ and related SysV init commands.
- ***Project 8-2 Step 8 (pg 379)*** - `init` is no longer available in Fedora 45. Instead, run `systemctl isolate multi-user.target` to switch to runlevel 3. 
- ***Project 8-2 Step 10 (pg 379)*** - Run `systemctl list-units --type=target` and note that the ***multi-user.target*** is loaded and active.
- ***Project 8-2 Step 11 (pg 379)*** - Run `systemctl isolate rescue.target` to switch to rescue.target.  
- ***Project 8-2 Step 12 (pg 379)*** - Run `systemctl list-units --type=target` and note that the ***rescue.target*** is loaded and active.
- ***Project 8-4 Step 6 (pg 381)*** -  `telinit` is no longer available in Fedora 45. Instead run `systemctl isolate reboot.target` to reboot the system by switching to reboot.target.
- ***Project 12-6 Step 4 (pg 562)*** - TigerVNC now limits passwords to 8 characters, so you should enter one that is shorter than `LINUXrocks` (e.g., `LXrocks!`).

## Changes for Ubuntu Server 26.04 LTS (x86_64 or aarch64) 

- ***Project 10-3 Step 2 (pg 454)*** - This step is no longer necessary as rsyslog is now installed by default.
- ***Project 12-1 Step 20 (pg 558)*** - Ubuntu now stores network configuration in 00-installer-config.yaml. Consequently, you must run the `cat /etc/netplan/00-installer-config.yaml` command in this step. 
- ***Project 13-3 Step 2 (pg 612)*** - Ubuntu now calls the ntp and ntpdate packages ntpsec and ntpsec-ntpdate, respectively. Consequently, you must run the `apt install ntpsec ntpsec-ntpdate -y` command in this step.

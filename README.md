# CengageLinux
Updates for ***Linux+ and LPIC-1 Guide to Linux Certification (6th Edition)***, ISBN: 9798214000800

In this book, you install virtual machines of the latest Fedora Workstation and Ubuntu Server for your architecture (x86_64 or aarch64) on a Windows or macOS system.

New versions of each Linux distribution are released frequently. While nearly all steps within the hands-on projects in this book will remain the same for newer versions of Linux, there may be some steps that need to be modified. You can find these steps for each new version of Fedora Workstation and Ubuntu Server in this repository. You will also find any hands-on project steps that need to be modified because of new versions of Windows or macOS.

This book was written using the latest distribution available at the time of writing:
- Fedora Workstation 36, and
- Ubuntu Server 22.04

## Changes for Fedora Workstation 37 (x86_64 or aarch64)
- ***Project 2-6 Step 2 (pg 70)*** - Before running this step, execute the `dnf -y install cron` command to install the cron daemon. Starting with Fedora 37, this daemon is not installed by default. THIS IS NOT AN ACTUAL ERROR BUT A TEMPLATE LINE ONLY!

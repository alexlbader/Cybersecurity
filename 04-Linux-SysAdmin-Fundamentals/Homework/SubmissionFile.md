## Week 4 Homework Submission File: Linux Systems Administration

Please edit this file by adding the solution commands on the line below the prompt.

Save and submit the completed file for your homework submission.


### Step 1: Ensure/Double Check Permissions on Sensitive Files

1. Permissions on `/etc/shadow` should allow only `root` read and write access.
sudo chmod 600 /etc/shadow
    - Command to inspect permissions:
ls -l /etc/shadow
    - Command to set permissions (if needed):
sudo chmod
2. Permissions on `/etc/gshadow` should allow only `root` read and write access.
sudo chmod 600 /etc/gshadow
    - Command to inspect permissions:
ls -l
    - Command to set permissions (if needed):
sudo chmod
3. Permissions on `/etc/group` should allow `root` read and write access, and allow everyone else read access only.
sudo chmod 644 etc/group
    - Command to inspect permissions:
ls -l
    - Command to set permissions (if needed):
sudo chmod
4. Permissions on `/etc/passwd` should allow `root` read and write access, and allow everyone else read access only.
sudo chmod 644 /etc/passwd
    - Command to inspect permissions:
ls -l
    - Command to set permissions (if needed):
sudo chmod
### Step 2: Create User Accounts

1. Add user accounts for `sam`, `joe`, `amy`, `sara`, and `admin`.

    - Command to add each user account (include all five users):
sudo useradd sam
sudo useradd joe
sudo useradd amy
sudo useradd sara
sudo useradd admin
2. Ensure that only the `admin` has general sudo access.
sudo -l
    - Command to add `admin` to the `sudo` group:
sudo usermod -G sudo admin
### Step 3: Create User Group and Collaborative Folder

1. Add an `engineers` group to the system.
sudo addgroup engineers
    - Command to add group:
sudo addgroup
2. Add users `sam`, `joe`, `amy`, and `sara` to the managed group.
sudo usermod -aG engineers sam
sudo usermod -aG engineers joe
sudo usermod -aG engineers amy
sudo usermod -aG engineers sara
    - Command to add users to `engineers` group (include all four users):
sudo usermod -aG engineers sam
sudo usermod -aG engineers joe
sudo usermod -aG engineers amy
sudo usermod -aG engineers sara
3. Create a shared folder for this group at `/home/engineers`.
sudo mkdir /home/engineers
    - Command to create the shared folder:
sudo mkdir
4. Change ownership on the new engineers' shared folder to the `engineers` group.

    - Command to change ownership of engineer's shared folder to engineer group:
sudo chown :engineers /home/engineers
### Step 4: Lynis Auditing

1. Command to install Lynis:
sudo apt install lynis
2. Command to see documentation and instructions:
man Lynis
3. Command to run an audit:
sudo Lynis audit System
4. Provide a report from the Lynis output on what can be done to harden the system.
sudo apt install libpam-tmpdir
sudo apt install libpam-usb
sudo apt install apt-listbugs
sudo apt install apt-listchanges
sudo apt install needrestart
sudo apt install debsecan
sudo apt install debsums
sudo apt install fail2ban
grub-mkpasswd-pbkdf2

    - Screenshot of report output:


### Bonus
1. Command to install chkrootkit:
sudo apt chkrootkit
2. Command to see documentation and instructions:
man chrootkit
3. Command to run expert mode:
sudo chkrootkit -x
4. Provide a report from the chrootkit output on what can be done to harden the system.
    - Screenshot of end of sample output:
    
---
© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.

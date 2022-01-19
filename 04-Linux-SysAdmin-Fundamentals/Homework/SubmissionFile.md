## Week 4 Homework Submission File: Linux Systems Administration

Please edit this file by adding the solution commands on the line below the prompt.

Save and submit the completed file for your homework submission.


### Step 1: Ensure/Double Check Permissions on Sensitive Files

1. Permissions on `/etc/shadow` should allow only `root` read and write access.

    - Command to inspect permissions: ls -l /etc/shadow

    - Command to set permissions (if needed): sudo chmod 600 /etc/shadow

2. Permissions on `/etc/gshadow` should allow only `root` read and write access.

    - Command to inspect permissions: ls -l /etc/gshadow

    - Command to set permissions (if needed): sudo chmod 600 /etc/gshadow

3. Permissions on `/etc/group` should allow `root` read and write access, and allow everyone else read access only.

    - Command to inspect permissions: ls -l /etc/group

    - Command to set permissions (if needed): sudo chmod 640 /etc/group

4. Permissions on `/etc/passwd` should allow `root` read and write access, and allow everyone else read access only.

    - Command to inspect permissions: ls -l /etc/passwd

    - Command to set permissions (if needed): sudo chmod 644 /etc/passwd

### Step 2: Create User Accounts

1. Add user accounts for `sam`, `joe`, `amy`, `sara`, and `admin`.

    - Command to add each user account (include all five users): sudo useradd sam, sudo useradd joe, sudo useradd amy, sudo useradd sara, sudo useradd admin

2. Ensure that only the `admin` has general sudo access.  

    - Command to add `admin` to the `sudo` group: sudo usermod -a -G sudo admin

### Step 3: Create User Group and Collaborative Folder

1. Add an `engineers` group to the system.

    - Command to add group: sudo groupadd engineers

2. Add users `sam`, `joe`, `amy`, and `sara` to the managed group.

    - Command to add users to `engineers` group (include all four users): sudo usermod -a -G engineers sam, sudo usermod -a -G engineers joe, sudo usermod -a -G engineers amy, sudo usermod -a -G engineers sara,

3. Create a shared folder for this group at `/home/engineers`.

    - Command to create the shared folder: sudo mkdir -p /home/engineers

4. Change ownership on the new engineers' shared folder to the `engineers` group.

    - Command to change ownership of engineer's shared folder to engineer group: sudo chmod -R 775 /home/engineers

### Step 4: Lynis Auditing

1. Command to install Lynis: sudo apt-get install lynis -y

2. Command to see documentation and instructions: sudo lynis --help

3. Command to run an audit: sudo lynis audit system

4. Provide a report from the Lynis output on what can be done to harden the system.

    - Screenshot of report output:
     Lynis security scan details:

  Hardening index : 57 [###########         ]
  Tests performed : 240
  Plugins enabled : 1

  Components:
  - Firewall               [V]
  - Malware scanner        [V]

  Lynis Modules:
  - Compliance Status      [?]
  - Security Audit         [V]
  - Vulnerability Scan     [V]

  Files:
  - Test and debug information      : /var/log/lynis.log
  - Report data                     : /var/log/lynis-report.dat

================================================================================
  Notice: Lynis update available
  Current version : 262    Latest version : 307
================================================================================

  Lynis 2.6.2

  Auditing, system hardening, and compliance for UNIX-based systems
  (Linux, macOS, BSD, and others)

  2007-2018, CISOfy - https://cisofy.com/lynis/
  Enterprise support available (compliance, plugins, interface and tools)

================================================================================

  [TIP]: Enhance Lynis audits by adding your settings to custom.prf (see /etc/lynis/default.prf for all settings)



### Bonus
1. Command to install chkrootkit: sudo apt install chkrootkit

2. Command to see documentation and instructions: sudo chkrootkit -h

3. Command to run expert mode: sudo chkrootkit -x

4. Provide a report from the chrootkit output on what can be done to harden the system.
    - Screenshot of end of sample output:
    2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.4IbixKDKqM
2022-01-19 17:07:06 Info: temporary file /tmp/lynis.xSLGhjmf8f was already removed
2022-01-19 17:07:06 Info: temporary file /tmp/lynis.rBACYoGbtd was already removed
2022-01-19 17:07:06 Info: temporary file /tmp/lynis.QBjEFlglL2 was already removed
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.3bzujLvCq3
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.mIDoEkftMQ
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.mCi9bcQ4FM
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.uiM3mwJDUk
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.PdfZmSftCQ
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.oDVSRt2bI0
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.AwyzIrNT8W
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.FUAORM3JXi
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.JP9ZFgB50Z
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.d9phdoejmS
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.PnNUNwHlR9
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.eCM6K2Fvw5
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.AUgWyvVc5p
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.7n3KiuLsq9
2022-01-19 17:07:06 Action: removing temporary file /tmp/lynis.iqPHZKzELW
2022-01-19 17:07:06 Lynis ended successfully.


---
© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.

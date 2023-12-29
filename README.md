<a name="readme-top"></a>
<div align="center">

# Born2beRoot 󰹑

> an introduction to _**the wonderful world of virtualization**_.

<p>
    <img src="https://img.shields.io/badge/score-125%20%2F%20100-success?style=for-the-badge" />
    <img src="https://img.shields.io/github/languages/count/PedroZappa/Born2beRoot?style=for-the-badge&logo=" />
    <img src="https://img.shields.io/github/languages/top/PedroZappa/Born2beRoot?style=for-the-badge" />
    <img src="https://img.shields.io/github/last-commit/PedroZappa/Born2beRoot?style=for-the-badge" />
</p>

</div>

![VM MEME](IMG/VM_MEME.jpeg)

# About

This project teaches how to setup a server implementing strict rules. To complete this project a **Virtual Machine** (using **VirtualBox** or **UTM**) must be build following specific instructions.

___

## Constraints
- [ ] Only minimum services must be installed;
- [ ] X.org or any other equivalent graphics servers are forbidden;
- [ ] Only either the latest stable version of **Debian** or **Rocky** should be used;
- [ ] **Firewall**
> - For **Debian** **AppArmor** must be running at startup;
> - For **Rocky**, **SELinux** must be launched at startup configured in accordance with the project's requirements;
- [ ] At least 2 encrypted partitions must be created using **LVM**;

![Partitions IMG](IMG/partitions.jpeg)

- [ ] An **SSH** service must be running on port 4242 only;
- [ ] For security reasons it must NOT be possible to connect using **SSH** as `root`;
- [ ] The operating system must be configured with a **Firewall**:
> - In the case of Debian, the **UFW** firewall leaving only port 4242 open.
> - In the case of Rocky, **firewalld**;
- [ ] The firewall must be active at startup;
- [ ] The **hostname** of the virtual machine should be your login with 42 appended;
- [ ] Know how to modify the **hostname**;
- [ ] Implement a strong password policy;
- [ ] Install and configure **sudo** following strict rules;
- [ ] Besides `root` user, a user with your login as username must be defined;
- [ ] This user must belong to `user42` and **sudo** groups;
- [ ] Know the difference between **apt** and **aptitude**;

___
## Password Policy

- [ ] The password must expire every 30 days;
- [ ] Minimum number of days before modifying the password is allowed should be set to 2;
- [ ] The user must be sent a message 7 days before their password expires;
- [ ] The password must be at least 10 characters long;
- [ ] Must contain an uppercase letter, a lowercase letter, and a number;
- [ ] It must not contain more than 3 consecutive identical characters;
- [ ] The password must note contain the name of the user;
- [ ] The password must have at least 7 characters that are not part of the former password (Doesn't apply to the `root` password);

___
## Configuration Setup

To create a strong configuration for a **sudo** group the following requirements must be met:

- [ ] Authentication using **sudo** has to be limited to 3 attempts in the event of an incorrect password;
- [ ] A custom message has to be displayed if an error due to a wrong password occurs when using **sudo**;
- [ ] Each action using **sudo** must be archived, both inputs and outputs. The log file must be saved in the `/var/log/sudo/` folder;
- [ ] **TTY mode** has to be enabled for security reasons;
- [ ] Also for security reasons, the path that can be used by **sudo** must be restricted;
Ex.: `/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin`

___
## Monitoring Script

A simple script written in **bash** launched at startup, should display information on the terminal every 10 minutes (check out **wall**):

- [ ] The architecture of your operating system and its kernel version;
- [ ] The number of physical processors;
- [ ] The number of virtual processors;
- [ ] The current available **RAM** on the server and its utilization rate as a percentage;
- [ ] The current available **Memory** on the server and its utilization rate as a percentage;
- [ ] The current utilization of the current processor as a percentage;
- [ ] The date and time of the last reboot;
- [ ] Whether **LVM** is active or not;
- [ ] The number of active connections;
- [ ] The number of users using the server;
- [ ] The **IPv4** address of your server and its **MAC Address**;
- [ ] The number of commands executed with the **sudo** command;
- [ ] The banner is optional;
- [ ] No errors must be visible;
- [ ] It must be possible to interrupt the script without modifying it;

> [!NOTE]
> Take a look at **crontab**;

An example of the script's output:

![Monitoring Script IMG](IMG/monitoring.jpeg)
___

## Bonus

- [ ] Set up partitions as to match a similar structure to the one below:

![Partitions Bonus IMG](IMG/partitions_bonus.jpeg)

- [ ] Set up a functional **WordPress** website with the following services: **lighttpd**, **MariaDB** and **PHP**;
- [ ] Set up a service of your choice that you think is useful (**NGINX** / **Apache2** excluded!)

> [!Important]
> To complete the bonus part, there is the possibility of setting up extra services. In this case, you may open more ports to suit your needs. Of course, the **UFW**/**Firewalld** rules has to be adapted accordingly.

___

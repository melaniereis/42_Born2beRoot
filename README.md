# Born2beRoot
42 Project : Born2beRoot

## Commands Glossary

### System Commands

- Become root:
```sh
su
```

- Shutdown the VM:
```sh
systemctl poweroff
```

- Reboot the VM
```sh
systemctl reboot
```

- Change `hostname`:
```sh
sudo hostnamectl set-hostname <hostname>
# And then change old user name to new one in:
sudo vim /etc/hosts
# and also
sudo vim /etc/hostname
# Reboot to apply changes
sudo reboot hostnamectl
```

- Get system login password policy file:

```sh
sudo vim /etc/login.defs
```

- Get user's password policy:

```sh
sudo vim /etc/pam.d/common-password
```

- Get system architecture:

```sh
uname -a
```

- Get cpu info:
```sh
sudo vim /proc/cpuinfo
```

- Get memory info:


```sh
free
```

- Get disk info:
```sh
df
```

- Display processes:

```sh
top
# Or
vmstat

```

- Get boot info:
```sh
who -b
```

- List block devices:

```sh
lsblk
```

- Check `users`:

```sh
users
# or for more info
w
```

- Show routing, network devices, interfaces and tunnels:

```sh
ip --color a
# Or, specifically for interfaces
vim /etc/network/interfaces
```


- Check all system sockets:

```sh
ss -tunlp
```


- Get system's `crontab`:

```sh
crontab -u root -e
```

- Check if there is a `GUI` installed:

```sh
ls /usr/bin/*session
```

___

### `sudo` Commands

- Check `sudo`'s version and other stats:

```sh
sudo -V
# or
dpkg -s sudo | grep Status
```

- Create a new user:
```sh
sudo adduser <username>
```

- Remove a user:

```sh
sudo deluser <username>
```

- Change a user's password:

```sh
sudo passwd <username>
```

- Create a new group:

```sh
sudo addgroup <groupname>
```

- Add a user to a group:

```sh
sudo adduser <username> <group>
```

- Get `PAM` password policy:
```sh
sudo vim /etc/pam.d/common-password
```

- Get `sudo_config` policy file:
```sh
sudo vim /etc/sudoers.d/sudo_config
```

- Get `sudo` log file:

```sh
sudo vim /var/log/sudo/sudo_config
```

- Get the system's journal

```sh
journalctl
```

___

### `ssh` Commands

- Get `hostname`:
```sh
hostname -I
```

- Connect to a remote host:
```sh
ssh -p <port> <username>@<hostname>
```

- Disconnect from a remote host:

```sh
exit
```

- Get `OpenSSH` server process config:

```sh
vim /etc/ssh/sshd_config
```

- Get `ssh` system-wide config:

```sh
vim /etc/ssh/ssh_config
```

- Restart the `OpenSSH` service:

```sh
sudo systemctl restart ssh
```


- Get `ssh` service status:

```sh
sudo service sshd status
```



### `ufw` Commands

- Start `ufw`:

```sh
sudo ufw enable
```

- Stop `ufw`:

```sh
sudo ufw disable
```

- Get `ufw` status:

```sh
sudo ufw status
```

- Open a port:

```sh
sudo ufw allow <port>
```

- Close a port:

```sh
sudo ufw delete <port>
```

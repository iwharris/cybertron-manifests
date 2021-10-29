Copy files from ../raspberry-pi/boot into the boot partition of the configured SD card, updating values where needed

NOTE user-data doesn't seem to be working - it does not change the hostname and/or users

## Alternate setup instead of user-data

### Update hostname

```bash
# Change hostname
sudo hostnamectl set-hostname k8s1

# Change hosts file
sudo nano /etc/hosts

sudo reboot -h now
```

### Generate SSH keypair and copy it to the remote:

```bash
ssh-copy-id -i $HOME/.ssh/k8s.pub ubuntu@192.168.100.11
```

### Disable password login in SSH

```bash
sudo nano /etc/ssh/sshd_config
```

Set up the file as follows

```
ChallengeResponseAuthentication no
PasswordAuthentication no
UsePAM no
PermitRootLogin no
PermitRootLogin prohibit-password
PrintMotd yes
```

```bash
sudo service ssh restart
```

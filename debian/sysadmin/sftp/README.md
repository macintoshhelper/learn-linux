# Learn Debian SFTP

## Getting Started
null

## Setting up SFTP with full file permissions
1. Run these CLI commands:

```sh
apt-get update
apt-get -y install bindfs

mkdir -p /home/<sftp-username>/websites/<website-url>
chown -Rf <sftp-username>:<sftp-username> /home/<sftp-username>/websites
chmod -Rf 770 /home/<sftp-username>/websites

nano /etc/fstab
```
2. Add this line:
```
bindfs#/var/www/<website-url> /home/<sftp-username>/websites/<website-url> fuse force-user=<sftp-username>,force-group=<sftp-username>,create-for-user=www-data,create-for-group=www-data,create-with-perms=0770,chgrp-ignore,chown-ignore,chmod-ignore 0 0  
```

3. Run this CLI command:
```sh
mount /home/<sftp-username>/websites/<website-url>
```

## Resources
- [Solving Web File Permissions (bindfs)](http://blog.netgusto.com/solving-web-file-permissions-problem-once-and-for-all/)

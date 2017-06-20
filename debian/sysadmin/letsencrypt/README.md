#Let's Encrypt

## Installation:
```bash
echo 'deb http://ftp.debian.org/debian jessie-backports main' >> /etc/apt/sources.list
apt-get update
apt-get install certbot -t jessie-backports -y
```


## Webroot usage:
```bash
certbot certonly --webroot -w /var/www/example.com -d example.com -d www.example.com
```

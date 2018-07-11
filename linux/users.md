# Users

## Create new user on fresh server

```bash
sudo useradd --create-home -s /bin/bash deploy
sudo adduser deploy sudo
sudo passwd deploy

sudo mkdir /home/deploy/.ssh
sudo nano  /home/deploy/.ssh/authorized_keys # Paste your id_rsa.pub
sudo chown -R deploy:deploy /home/deploy/.ssh
```

# Permissions

## Change owner of file or folder

```
sudo chown -R user:group folder
```

## Allow command as sudo without password

**Example for Monit**:
```
# sudoers file
username ALL=(root) NOPASSWD:/usr/bin/monit unmonitor app_name, /usr/bin/monit monitor app_name, /bin/mv /tmp/monit.conf /etc/monit/conf.d/app_name.conf, /usr/bin/monit reload
```

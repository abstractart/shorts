# Logs

## Logrotate config for Rails

```
/var/www/[application_name]/shared/log/*.log {
    su
    daily
    missingok
    rotate 90
    compress
    delaycompress
    notifempty
    copytruncate
}
```

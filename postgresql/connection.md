# Connection

## Allow remote connection via password

1) Append this line to ```pg_hba.conf```
```conf
host     <db_name>      <username>     0.0.0.0/0               md5
```

2) Go to ```postgresql.conf```, uncomment and change ```listen_addresses```
```conf
#------------------------------------------------------------------------------
# CONNECTIONS AND AUTHENTICATION
#------------------------------------------------------------------------------

# - Connection Settings -

listen_addresses = '*'		# what IP address(es) to listen on;

```

3) Restart PostgreSQL Server
```
sudo service postgresql restart # Ubuntu
```

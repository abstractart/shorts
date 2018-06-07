
```
# Dump DB
pg_dump -Fc database > database.dump
# Create empty DB
createdb database_from_dump

# Restore with different role as owner
pg_restore --no-owner --role=your_role -d database_from_dump -n public database.dump
```



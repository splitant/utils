# Drupal utils

Some helpfull commands for Drupal

## Databases & files

### Clean and restore database (.sql version)

```bash
drush @dev.dev sql-drop;
drush sql-cli < <dump_name>.sql;
```

### Clean and restore database (.sql.gz version)

```bash
drush @dev.dev sql-drop -y && gunzip -c ./dump/<dump_name>.sql.gz | drush @dev.dev sql-cli;
```

### Backup database

```bash
drush @dev.dev sql-dump | gzip -9 > ./dump/<dump_name>.sql.gz;
```

Or more cleaned dump :

```bash
drush @dev.dev sql-dump --structure-tables-list='cache,cache_*' | gzip -9 > ./dump/<dump_name>.sql.gz;
```

### Backup files

```bash
tar -czvf /tmp/<files_dump_name>.tar.gz files;
```



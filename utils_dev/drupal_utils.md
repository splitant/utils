# Drupal utils

Some helpfull commands for Drupal

## Databases & files

### Clean and restore database (.sql version)

```bash
drush sql-drop;
drush sql-cli < <dump_name>.sql;
```

### Clean and restore database (.sql.gz version)

```bash
drush sql-drop -y && gunzip -c ./dump/<dump_name>.sql.gz | drush sql-cli;
```

### Backup database

```bash
drush sql-dump --result-file=auto --gzip;
```

Or more cleaned dump :

```bash
drush sql-dump --result-file=auto --gzip --structure-tables-list='cache,cache_*';
```

### Get superadmin temporary access

```bash
drush uli;
```
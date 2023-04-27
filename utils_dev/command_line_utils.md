# Command lines 

Some helpfull commands line.

#### Search all jpg images in the system and archive it.

```bash
find / -name *.jpg -type f -print | xargs tar -cvzf images.tar.gz
```

#### Download all the URLs mentioned in the url-list.txt file

```bash
cat url-list.txt | xargs wget –c
```

#### Update, upgrade and shutdown

```bash
sudo apt-get update -y && sudo apt-get upgrade -y && sudo apt-get dist-upgrade -y && sudo shutdown -h now
```

#### List lines file of 'pattern' occurence

```bash
grep -rnw '/path/to/somewhere/' -e 'pattern' 
```

#### Replace string in gzip file

```bash
gunzip < file.gz | sed -e 's/search_str/replace_str/g' | gzip -c > temp.gz;
mv temp.gz file.gz;
```

#### unzip file

```bash
gunzip -c <compressed-file>.gz > <decompressed-file>
```

#### Mysql dump

```bash
mysqldump -u"<user>" -h"<db_host>" -p "<db_name>" --single-transaction --create-options --extended-insert --complete-insert --databases --add-drop-database > dump_$(date +%d%m%Y-%H%M%S).sql
```

With gzip : 

```bash
mysqldump -u"<user>" -h"<db_host>" -p "<db_name>" --single-transaction --create-options --extended-insert --complete-insert --databases --add-drop-database | gzip > dump_$(date +%d%m%Y-%H%M%S).sql.gz
```

#### Mysql restore

```bash
mysql -u"<user>" -h"<db_host>" -p "<db_name>" < <dump_name>.sql
```

With gzip : 

```bash
zcat <dump_name>.sql.gz | mysql -u"<user>" -h"<db_host>" -p "<db_name>"
```

#### Backup files

```bash
tar -czvf <directory>.tar.gz <directory>;
```

#### List services with port used

```bash
netstat -tulpn
```

#### List services or processes

```bash
ps aux | grep -i <service_name> 
```

#### Check server access

```bash
telnet <server_name_or_ip> <port>
```
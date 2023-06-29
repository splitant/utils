# Command lines 

Some helpfull commands line.

## Sources

* [Cheat](https://github.com/cheat/cheat)
* [ExplainShell](https://explainshell.com/)

### Search all jpg images in the system and archive it.

```bash
find / -name *.jpg -type f -print | xargs tar -cvzf images.tar.gz
```

### Download all the URLs mentioned in the url-list.txt file

```bash
cat url-list.txt | xargs wget –c
```

### Display which distro is installed

```bash
cat /etc/issue
```

### Directory size

```bash
du -sh <directory_name>
```

all sub-directories size : 

```bash
du -h --max-depth=1
```

### Update, upgrade and shutdown

```bash
sudo apt update -y && sudo apt upgrade -y && sudo apt dist-upgrade -y && sudo shutdown -P now
```

### List lines file of 'pattern' occurence

```bash
grep -rnw '/path/to/somewhere/' -e 'pattern' 
```

### Replace string in gzip file

```bash
gunzip < file.gz | sed -e 's/search_str/replace_str/g' | gzip -c > temp.gz;
mv temp.gz file.gz;
```

### Unzip file

```bash
gunzip -c <compressed-file>.gz > <decompressed-file>
```

### Mysql dump

```bash
mysqldump -u"<user>" -h"<db_host>" -p "<db_name>" --single-transaction --create-options --extended-insert --complete-insert --databases --add-drop-database > dump_$(date +%d%m%Y-%H%M%S).sql
```

With gzip : 

```bash
mysqldump -u"<user>" -h"<db_host>" -p "<db_name>" --single-transaction --create-options --extended-insert --complete-insert --databases --add-drop-database | gzip > dump_$(date +%d%m%Y-%H%M%S).sql.gz
```

### Mysql restore

```bash
mysql -u"<user>" -h"<db_host>" -p "<db_name>" < <dump_name>.sql
```

With gzip : 

```bash
zcat <dump_name>.sql.gz | mysql -u"<user>" -h"<db_host>" -p "<db_name>"
```

### Backup files

```bash
tar -czvf <directory>.tar.gz <directory>;
```

### List services with port used

```bash
netstat -tulpn
```

### List services or processes

```bash
ps aux | grep -i <service_name> 
```

### Check server access

```bash
telnet <server_name_or_ip> <port>
```

### Download content from URL

```bash
curl -o <filename> <url>
```

with following redirections : 

```bash
curl -L -o <filename> <url>
```

with only HTTP headers : 

```bash
curl -I <url>
```

### Patch file

```bash
patch -p1 < file.patch
```

Revert a patch : 

```bash
patch -R -p1 < file.patch
```
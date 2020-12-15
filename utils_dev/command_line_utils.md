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

#### Save today date

```bash
today_dump=$(date +%d%m%Y-%H%M%S);
```

#### List services with port used

```bash
netstat -tulpn
```



# 🔍 Forensic

Search for last modified files (for 1 day):

```bash
find / -newermt "1 day ago" -ls
```

Last login:

```bash
lastlog
last
```

All crontabs:

```shell
for user in $(cat /etc/passwd | cut -f1 -d: ); do echo $user; crontab -u $user -l; done
```

## Persisitence

Folders:

```
/etc/cron*/
/etc/incron.d/*
/etc/init.d/*
/etc/rc*.d/*
/etc/systemd/system/*
/etc/update.d/*
/var/spool/cron/*
/var/spool/incron/*
/var/run/motd.d/*
```

Files:

```
/etc/passwd
/etc/sudoers
/home/<user>/.ssh/authorized_keys
/home/<user>/.bashrc
```

Sort files in current directory by date:

```
find . -printf "%T@ %Tc %p\n" | sort -n
```

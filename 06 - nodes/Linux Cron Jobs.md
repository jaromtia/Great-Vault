#resources/linux 

```
05 00 * * * /tmp/backup.sh
```

minute hour day month year file 

# File Locations

Global
```
/etc/crontab
/etc/cron.d
/etc/cron.daily
/etc/cron.hourly
/etc/cron.monthly
/etc/cron.weekly
/etc/cron.yearly
```

User Level

```
/var/spool/cron/crontabs
```

# Commands 

```bash
sudo crontab -u [user] -l 
```
-u = user
-l = list 
![[Pasted image 20250130044744.png]]


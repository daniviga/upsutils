## upsnotify 

A small script to use with NUT for notify via mail.

How to use:

- Edit script variables, first of all `$UPSNAME` (currently supporting only one UPS at time)
- Put `upsnotify` somewhere (for example `/usr/local/bin`)
- Make it executable (`chmod +x /usr/local/bin/upsnotify`)
- Edit `/etc/ups/upsmon.conf`
 - Set `NOTIFYCMD` to script path (`NOTIFYCMD /usr/local/bin/upsnotify`)
 - Enable `EXEC` in `NOTIFYFLAG`

For example:

```
NOTIFYFLAG ONLINE       SYSLOG+EXEC
NOTIFYFLAG ONBATT       SYSLOG+EXEC
NOTIFYFLAG LOWBATT      SYSLOG+EXEC
NOTIFYFLAG FSD          SYSLOG+EXEC
NOTIFYFLAG COMMOK       SYSLOG+EXEC
NOTIFYFLAG COMMBAD      SYSLOG+EXEC
NOTIFYFLAG SHUTDOWN     SYSLOG+EXEC
NOTIFYFLAG REPLBATT     SYSLOG+EXEC
NOTIFYFLAG NOCOMM       SYSLOG+EXEC
NOTIFYFLAG NOPARENT     SYSLOG+EXEC
```
- Save and restart nut-monitor (`systemctl restart nut-monitor.service`)


# Fast update date and time when OpenWrt connect internet
## install fping wget ntpdate

```bash
opkg update && opkg install fping wget ntpdate
```

## install ntpupdate script

```bash
wget --show-progress --progress=bar:force -qO /usr/bin/ntpupdate https://raw.githubusercontent.com/laksa19/openwrt-tools/master/ntp-update/ntpupdate && chmod +x /usr/bin/ntpupdate 
```

## run script at startup

```bash
(crontab -l 2>/dev/null; echo "@reboot /usr/bin/ntpupdate") | crontab -
```

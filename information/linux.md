
### Aumentar el limite de observacion para linux

```
echo 65536 | sudo tee -a /proc/sys/fs/inotify/max_user_watches

echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```

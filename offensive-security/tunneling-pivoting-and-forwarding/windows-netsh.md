# (Windows) netsh

Using built-in netsh executable to forward port:

```powershell
netsh interface portproxy add v4tov4 listenport=2222 listenaddress=192.168.205.64 connectport=4545 connectaddress=10.4.205.215
```

Unblock port blocked by firewall:

```powershell
netsh advfirewall firewall add rule name="port_forward_ssh_2222" protocol=TCP dir=in localip=192.168.205.64 localport=2222 action=allow
```

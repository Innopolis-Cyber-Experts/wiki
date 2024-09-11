# SSH

Forward one port:

```bash
ssh -N -L 0.0.0.0:4455:172.16.50.217:445 database_admin@10.4.50.215
```

Start socks proxy:

```bash
ssh -N -D 0.0.0.0:9999 database_admin@10.4.50.215
```

Remote port forwarding (reverse):

```bash
ssh -N -R 127.0.0.1:2345:10.4.50.215:5432 kali@192.168.118.4
```

Dynamic remote (socks):

```bash
ssh -N -R 9998 kali@192.168.118.4
```

sshuttle:

```bash
sshuttle -r database_admin@192.168.50.63:2222 10.4.50.0/24 172.16.50.0/24
```

Plink:

```powershell
plink.exe -ssh -l kali -pw kali -R 127.0.0.1:9833:127.0.0.1:3389 192.168.118.4
```

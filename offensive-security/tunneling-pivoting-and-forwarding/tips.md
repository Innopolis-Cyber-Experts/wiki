# Tips

If `nmap` not works via `proxychains` - update it

SSH via socks:

```
ssh -o ProxyCommand='ncat --proxy-type socks5 --proxy 127.0.0.1:1080 %h %p' database_admin@10.4.50.215
```

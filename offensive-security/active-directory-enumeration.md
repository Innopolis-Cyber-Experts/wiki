# Active Directory enumeration

* smbclient

Download all recursively:

```
mask ""
recurse ON
prompt OFF
lcd .
mget *
```

* enum4linux:

```bash
enum4linux 10.10.11.207 | tee enum4linux.txt
```

```bash
enum4linux -u '%' -a  10.10.11.207 | tee enum4linux.txt
```

* ldapsearch

```bash
ldapsearch -H ldap://domain.com/ -x -s base -b '' "(objectClass=*)" "*" + > ldap-basic-info.txt
```

* rpcdump

```
rpcdump.py <IP>
```

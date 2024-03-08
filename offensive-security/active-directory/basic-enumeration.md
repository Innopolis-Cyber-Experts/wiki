# Basic Enumeration

### NetExec (former CrackMapExec)

Scan network for SMB hosts (and get some useful info like hostname and domain):

```bash
nxc smb 192.168.1.0/24
```

### smbclient

List all shares:

```bash
smbclient -L //192.168.2.10/
```

Connect to share:

```bash
smbclient //192.168.2.10/Files
```

Download all recursively:

```
mask ""
recurse ON
prompt OFF
lcd .
mget *
```

### enum4linux

Basic usage:

```bash
enum4linux 10.10.11.207 | tee enum4linux.txt
```

Sometimes server does not allow session as guest, but allows null session (with empty username):

```bash
enum4linux -u '%' -a  10.10.11.207 | tee enum4linux.txt
```

### ldapsearch

```bash
ldapsearch -H ldap://domain.com/ -x -s base -b '' "(objectClass=*)" "*" + > ldap-basic-info.txt
```

### rpcdump

```
rpcdump.py <IP>
```

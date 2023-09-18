# AtomicRed

### Exlopre Atomic Red Team
https://atomicredteam.io/

- Installing Atomic PS framework

```PS
IEX (IWR 'https://raw.githubusercontent.com/redcanaryco/invoke-atomicredteam/master/install-atomicredteam.ps1' -UseBasicParsing); Install-AtomicRedTeam -getAtomics
```

- this might be needed as well:
```PS
Set-ExecutionPolicy Bypass -Scope CurrentUser
```

- add the folder to the exclusion list
```PS
Add-MpPreference -ExclusionPath C:\AtomicRedTeam\
```

- Import the module
```PS
Import-Module "C:\AtomicRedTeam\invoke-atomicredteam\Invoke-AtomicRedTeam.psd1" -Force
```

- if a test need a prerequisite, you can check it with this
```PS
Invoke-AtomicTest T1485 -TestNumbers 1 -CheckPrereq
```

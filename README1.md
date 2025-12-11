# How to Update Patches On windows

## Step 1:
* Open Powershell as **Administrator**
* Run the command given below:-
 
```
New-ItemProperty -Path "HKLM:\SOFTWARE\OpenSSH" `
>>     -Name "DefaultShell" -Value "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe" `
>>     -PropertyType String -Force
DefaultShell : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
PSPath       : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\OpenSSH
PSParentPath : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE
PSChildName  : OpenSSH
PSDrive      : HKLM
PSProvider   : Microsoft.PowerShell.Core\Registry
```

* Restart SSH Service
```
Restart-Service sshd
```

## Step 2:

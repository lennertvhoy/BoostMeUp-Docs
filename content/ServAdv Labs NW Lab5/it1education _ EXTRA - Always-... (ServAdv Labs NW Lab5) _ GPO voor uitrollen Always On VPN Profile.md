---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO voor uitrollen Always On VPN Profile"
last_updated: "2026-02-05"
---

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO voor uitrollen Always On VPN Profile/1635578817_practice.png)

## 

## GPO voor uitrollen Always On VPN Profile for user tunnel

##### In deze deelopdracht maken we een GPO aan om het profiel voor de Always-On VPN uit te rollen voor leden van de groep 'VPN Users'.

##### 

##

* Log in op de server SRV-MAN-01 met de domain administrator van het netwerk AD.Training.com
* Open de console "Group Policy Management"
* Maak een nieuwe GPO aan met de naam "Set Always On VPN user tunnel"

> Zorg ervoor dat de GPO enkel wordt toegepast op de groep "VPN Users".  
> Kopieer ook de ID van deze GPO (deze is terug te vinden onder het tabblad 'Details')

* Open 'Powershell ISE' als administrator en kopieer onderstaand script in het scriptvenster: (pas ID van GPO aan !!)
```
If (Test-Connection -ComputerName SRV-DC-01 -Quiet -Count 1) {
    Copy-Item "\\SRV-DC-01\SysVol\AD.Training.com\Policies\{<ID GPO 'Set Always On VPN user tunnel'>}\User\Scripts\Logon\rasphone.pbk" -Destination "C:\Users\$env:USERNAME\AppData\Roaming\Microsoft\Network\Connections\Pbk"  
}
```

+ Bewaar dit script als "CopyPhoneBook.ps1" in het volgende path: (pas ID van GPO aan !!)

```
\\SRV-DC-01\SYSVOL\AD.Training.com\Policies\{<ID GPO 'Set Always On VPN user tunnel'>}\User\Scripts\Logon
```
* Open een nieuw tabblad in 'Powershell ISE' en kopieer onderstaand script in het scriptvenster:
```
$Path = "HKLM:\SYSTEM\CurrentControlSet\Services\RasMan\Config"
if (Test-Path -Path $Path)
{
    $AppendedDnsSuffixSearchList = "AD.Training.com"
    $AutoTriggerProfileEntryName = "AlwaysOnVPN"
    $AutoTriggerProfilePhonebookPath = "C:\Users\$env:USERNAME\AppData\Roaming\Microsoft\Network\Connections\Pbk\rasphone.pbk"
    $UserSID = ([System.Security.Principal.WindowsIdentity]::GetCurrent()).User.Value

    New-ItemProperty -Path $Path -Name "AppendedDnsSuffixSearchList" -Value $AppendedDnsSuffixSearchList -Force
    New-ItemProperty -Path $Path -Name "AutoTriggerDisabledProfilesList" -Force -PropertyType MultiString
    New-ItemProperty -Path $Path -Name "AutoTriggerProfileEntryName" -Value $AutoTriggerProfileEntryName -Force
    New-ItemProperty -Path $Path -Name "AutoTriggerProfilePhonebookPath" -Value $AutoTriggerProfilePhonebookPath -Force
    New-ItemProperty -Path $Path -Name "UserSID" -Value $UserSID -Force
}
```

+ Bewaar dit script als "SetAlwaysOnVPNAutoTrigger.ps1" in het volgende path: (pas ID van GPO aan !!)

```
\\SRV-DC-01\SYSVOL\AD.Training.com\Policies\{<ID GPO 'Set Always On VPN user tunnel'>}\User\Scripts\Logon
```
* Open de Run en ga naar het volgende path:
```
\\CL-W10-VPN\c$\Users\VPNAdmin\AppData\Roaming\Microsoft\Network\Connections\Pbk
```

+ Kopieer het bestand 'rasphone' en kopieer het naar: (pas ID van GPO aan
  !!)
```
\\SRV-DC-01\SYSVOL\AD.Training.com\Policies\{<ID GPO 'Set Always On VPN user tunnel'>}\User\Scripts\Logon
```

* Rechtsklik op de GPO 'Set Always On VPN user tunnel' en kies voor "Edit"

+ Ga binnen de console GPME naar het volgende pad:
```
User\Policies\Windows Settings\Scripts
```
+ Rechtsklik op 'Logon' en kies voor "Properties"

- Ga naar het tabblad 'Powershell Scripts"
- Klik op "Add..."

* Browse naar 'CopyPhoneBook.ps1' en klik op "Open"
* Klik op OK

- Klik op "Add..."

* Browse naar 'SetAlwaysOnVPNAutoTrigger.ps1' en klik op "Open"
* Klik op OK

- Klik op Apply en OK

* Link de GPO 'Set Always On VPN user tunnel' aan
  het domein

---


Video tonen/verbergen

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO voor uitrollen Always On VPN Profile/1635252706_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
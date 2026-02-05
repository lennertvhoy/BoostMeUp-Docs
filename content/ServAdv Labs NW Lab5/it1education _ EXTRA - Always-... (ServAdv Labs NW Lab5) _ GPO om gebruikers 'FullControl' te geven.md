---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO om gebruikers 'FullControl' te geven"
last_updated: "2026-02-05"
---

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO om gebruikers 'FullControl' te geven/1635578817_practice.png)

## 

## GPO om gebruikers 'FullControl' te geven op de Config-Key

##### In deze deelopdracht maken we een GPO aan om gebruikers de nodige rechten te geven op de Config-Key.

##### 

##

* Log in op de server SRV-MAN-01 met de domain administrator van het netwerk AD.Training.com
* Open de console "Group Policy Management"
* Maak een nieuwe GPO aan met de naam "Set local users FullControl RasMan Config"
* Open 'Powershell ISE' als administrator en kopieer onderstaand script in het scriptvenster: (pas ID van GPO aan !!)
```
# Registry path
$Path = "HKLM:\SYSTEM\CurrentControlSet\Services\RasMan\Config"
# Create registry path of non-existent
if (!(Test-Path -Path $Path))
{
    New-Item -Path $Path
}
# Set fullcontrol to users
$IdRef = [System.Security.Principal.NTAccount](".\Users")
$RegRights = [System.Security.AccessControl.RegistryRights]::FullControl
$InhFlags = [System.Security.AccessControl.InheritanceFlags]::None
$PrFlags = [System.Security.AccessControl.PropagationFlags]::None
$AcType = [System.Security.AccessControl.AccessControlType]::Allow
$Rule = New-Object System.Security.AccessControl.RegistryAccessRule ($IdRef, $RegRights, $InhFlags, $PrFlags, $AcType)
$Acl = Get-Acl $Path
$Acl.SetAccessRule($Rule)
$Acl | Set-Acl -Path $Path
```
* Bewaar dit script als "SetLocalUsersFullControlRasmanConfig.ps1" op de 'Desktop' van de gebruiker
* Kopieer het script 'SetLocalUsersFullControlRasmanConfig.ps1'
* Rechtsklik op de GPO 'Set local users FullControl RasMan Config' en kies voor
  "Edit"

+ Ga binnen de console GPME naar het volgende pad:
```
Computer\Policies\Windows Settings\Scripts
```
+ Rechtsklik op 'Startup' en kies voor "Properties"

- Ga naar het tabblad 'Powershell Scripts"
- Klik op "Show Files..."

* Plak hier het script 'SetLocalUsersFullControlRasmanConfig.ps1'
* Sluit het venster

- Klik op "Add..."

* Browse naar de locatie voor startup scripts en selecteer het script 'SetLocalUsersFullControlRasmanConfig.ps1'
* Klik op "Open"
* Klik op OK

* Link de GPO 'Set local users FullControl RasMan
  Config' aan het domein

---


Video tonen/verbergen

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO om gebruikers 'FullControl' te geven/1635252706_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
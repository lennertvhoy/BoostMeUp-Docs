---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO voor uitrollen Always On VPN Profile1"
last_updated: "2026-02-05"
---

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO voor uitrollen Always On VPN Profile1/1635578817_practice.png)

## 

## GPO voor uitrollen Always On VPN Profile for device tunnel

##### In deze deelopdracht maken we een GPO aan om het profiel voor de Always-On VPN uit te rollen voor leden van de groep 'VPN Computers'.

##### 

##

* Log in op de server SRV-MAN-01 met de domain administrator van het netwerk AD.Training.com
* Open de console "Group Policy Management"
* Maak een nieuwe GPO aan met de naam "Set Always On VPN device tunnel"

> Zorg ervoor dat de GPO enkel wordt toegepast op de groep "VPN Computers".

* Zorg ervoor dat de bestanden 'SampleDeviceTunnelVPNProfile.xml' en
  'CreateDeviceTunnelVPNProfile.ps1' terechtkomen op de server
  SRV-DC-01
* Selecteer en kopieer deze beide bestanden
* Rechtsklik op de GPO 'Set Always On VPN user tunnel' en kies voor "Edit"

+ Ga binnen de console GPME naar het volgende pad:
```
Computer\Policies\Windows Settings\Scripts
```
+ Rechtsklik op 'Startup' en kies voor "Properties"

- Ga naar het tabblad 'Powershell Scripts"
- Klik op "Show Files..."

* Plak beide bestanden hier
* Sluit het venster

- Klik op "Add..."

* Browse naar 'CreateDeviceTunnelVPNProfile.ps1' en klik op "Open"
* Onder Script Parameters geef je het volgende mee:
```
-xmlFilePath .\DeviceTunnelVPNProfile.xml -ProfileName "Always On VPN Device Tunnel"
```
* Klik op OK

- Klik op Apply en OK

* Link de GPO 'Set Always On VPN device tunnel'
  aan het domein

---


Video tonen/verbergen

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO voor uitrollen Always On VPN Profile1/1635252706_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
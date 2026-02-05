---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Configuratie NPS-server"
last_updated: "2026-02-05"
---

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Configuratie NPS-server/1635172893_practice.png)

## 

## Configuratie NPS-server

##### In deze deelopdracht configureren we de server 'SRV-NPS-01'.

##### 

##### 

* Log in op de server SRV-NPS-01 met de domain administrator van het netwerk AD.Training.com
* Open de command prompt als administrator en geef het volgende commando in:
```
certlm
```

> Dit opent de console 'Certificates' op de lokale computer.

* Klik op 'Personal'  en kies voor "Certificates"

> Controleer of het certificaat uitgerold is.

* Open de Server Manager en kies onder 'Manage' voor "Add Roles and Features"
* Selecteer "Role based or feature based installation"
* Bij het venster 'Select Server' kies je voor SRV-DC-01 en klik je op Next
* Bij het venster 'Server Roles' vink je "Network Policy and Access Services" aan en klik je op Next
> Bij het pop-upvenster klik je op "Add features".

* Bij het venster 'Features' klik je op Next
* Bij het venster 'Network Policy and Access Services' klik je op Next
* Bij het venster 'Confirmation' klik je op "Install"
* Bij het venster 'Results' klik je op "Close" om de wizard af te sluiten

* Open de console 'Network Policy Server'
* Rechtsklik op 'SRV-NPS-01 (local)' en kies voor "Register server in Active Directory"

> Bij het pop-upvenster klik je 2 maal op OK.

* Klik op 'Radius Clients and Servers' en ga naar "RADIUS Clients"
* Rechtsklik op "RADIUS Clients" en kies voor "New"
* Geef de volgende configuratie op en klik op OK:

+ Friendly name: SRV-RAS-01
+ Address: SRV-RAS-01.AD.Training.com

- Klik op "Verify" and "Resolve" om het IP-adres te verkrijgen
- Klik daarna op OK

+ Shared secret: Geef 2 keer "Azerty01" mee

* Klik op 'SRV-NPS-01 (local)' en controleer dat "RADIUS server for DialUP or VPN Connections" is geselecteerd
* Klik nu op "Configure VPN or Dial-Up" en geef de volgende configuratie mee:

+ Onder 'Select Dial-Up or VPN Connections Type' kies je voor "Virtual Private Network (VPN) Connections" en klik op Next
+ Onder 'Specify Dial-Up or VPN Server' controleer je of SRV-RAS-01 aanwezig is (zoniet voeg je die toe) en klik op Next
+ Onder 'Configure Authentication Methods' geef je de volgende configuratie mee en klik op Next:

- Vink "Microsoft Encrypted Authentication version 2..." af
- Vink "Extensible Authentication Protocol" aan en selecteer "Microsoft Protected EAP (PEAP) aan
- Klik op "Configure..."

* Via "Remove" verwijder je "Secured password..."
* Via "Add" voeg je "Smart Card or other certificate" toe
* Klik 2 maal op OK

+ Onder 'Specify User Groups' voeg je de groep "VPN Users" toe en klik op Next
+ Onder 'Specify IP Filters' laat je de default staan en klik op Next
+ Onder 'Specify Encryption Settings' laat je de default staan en klik op Next
+ Onder 'Specify a Realm Name' laat je de default staan en klik op Next
+ Onder 'Completing...' klik je op "Finish"

---


Video tonen/verbergen

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Configuratie NPS-server/1635172910_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
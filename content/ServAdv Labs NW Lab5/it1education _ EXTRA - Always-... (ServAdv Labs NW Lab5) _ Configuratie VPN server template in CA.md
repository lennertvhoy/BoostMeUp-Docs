---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Configuratie VPN server template in CA"
last_updated: "2026-02-05"
---

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20Configuratie%20VPN%20server%20template%20in%20CA/1635172893_practice.png)

## 

## Configuratie VPN server template in CA

##### In deze deelopdracht configureren we de vpn server template in 'Certification Authority'.

##### 

##### 

* Log in op de server SRV-MAN-01 met de domain administrator van het netwerk AD.Training.com
* Open de console "Certification Authority"
* Klik op 'Training-DC-CA'
* Rechtsklik op 'Certificate Templates' en kies voor "Manage"
* In het venster 'Certificate Templates Console' rechtsklik je op 'RAS and IAS Server' en kies voor "Duplicate Template"

+ Onder het tabblad 'General' geef je de volgende configuratie:

- Template display name: VPN Server Authentication
- Template name: VPNServerAuthentication

+ Onder het tabblad 'Extensions' klik je op "Edit"

- Voeg "IP security IKE intermediate" toe en klik op OK

+ Onder het tabblad 'Security' geef je de volgende configuratie:

- Verwijder de groep "RAS and IAS Servers"
- Voeg via "Add..."de groep "VPN Servers" toe met de permissies 'Read' en 'Enroll'

+ Onder het tabblad 'Subject Name' geef je de volgende configuratie:

- Vink "Supply in the request" en klik op OK

+ Klik op "Apply" en OK om de wijzigingen toe te passen

* Sluit dit venster af
* Rechtsklik op 'Certificate Templates' en kies voor "New > Certificate Template to issue"

+ Kies voor de template 'VPN Server Authentication' en klik op OK

> Hierdoor zal de template toegevoegd worden aan de certificate templates.

---


Video tonen/verbergen

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20Configuratie%20VPN%20server%20template%20in%20CA/1635172910_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
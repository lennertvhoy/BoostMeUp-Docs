---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Configuratie computer template in CA"
last_updated: "2026-02-05"
---

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Configuratie computer template in CA/1635172893_practice.png)

## 

## Configuratie computer template in CA

##### In deze deelopdracht configureren we de computer template in 'Certification Authority'.

##### 

##### 

* Log in op de server SRV-MAN-01 met de domain administrator van het netwerk AD.Training.com
* Open de console "Certification Authority"
* Klik op 'Training-DC-CA'
* Rechtsklik op 'Certificate Templates' en kies voor "Manage"
* In het venster 'Certificate Templates Console' rechtsklik je op 'Computer' en kies voor "Duplicate Template"

+ Onder het tabblad 'General' geef je de volgende configuratie:

- Template display name: VPN Computer Authentication
- Template name: VPNComputerAuthentication
- Vink "Publish certificate in Active Directory" af

+ Onder het tabblad 'Security' geef je de volgende configuratie:

- Verwijder de groep "Domain Computers"
- Voeg via "Add..."de groep "VPN Computers" toe met de permissies 'Read', 'Enroll' en 'Autoenroll'

+ Onder het tabblad 'Compatibility' geef je de volgende configuratie:

- Bij 'Certification Authority' kies je voor "Windows Server 2016" en klik op OK
- Bij 'Certification recipient' kies je voor "Windows 10 / Windows Server 2016" en klik op OK

+ Klik op "Apply" en OK om de wijzigingen toe te passen

* Sluit dit venster af
* Rechtsklik op 'Certificate Templates' en kies voor "New > Certificate Template to issue"

+ Kies voor de template 'VPN Computer Authentication' en klik op OK

> Hierdoor zal de template toegevoegd worden aan de certificate templates.

---


Video tonen/verbergen

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Configuratie computer template in CA/1635172910_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
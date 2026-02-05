---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Configuratie user template in CA"
last_updated: "2026-02-05"
---

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Configuratie user template in CA/1635172893_practice.png)

## 

## Configuratie user template in CA

##### In deze deelopdracht configureren we de user template in 'Certification Authority'.

##### 

##### 

* Log in op de server SRV-MAN-01 met de domain administrator van het netwerk AD.Training.com
* Open de console "Certification Authority"
* Klik op 'Training-DC-CA'
* Rechtsklik op 'Certificate Templates' en kies voor "Manage"
* In het venster 'Certificate Templates Console' rechtsklik je op 'User' en kies voor "Duplicate Template"

+ Onder het tabblad 'General' geef je de volgende configuratie:

- Template display name: VPN User Authentication
- Template name: VPNUserAuthentication
- Vink "Publish certificate in Active Directory" af

+ Onder het tabblad 'Security' geef je de volgende configuratie:

- Verwijder de groep "Domain Users"
- Voeg via "Add..."de groep "VPN Users" toe met de permissies 'Read', 'Enroll' en 'Autoenroll'

+ Onder het tabblad 'Compatibility' geef je de volgende configuratie:

- Bij 'Certification Authority' kies je voor "Windows Server 2016" en klik op OK
- Bij 'Certification recipient' kies je voor "Windows 10 / Windows Server 2016" en klik op OK

+ Onder het tabblad 'Request Handling' geef je de volgende configuratie:

- Vink "Allow private key to be exported" af

+ Onder het tabblad 'Cryptography' geef je de volgende configuratie:

- Provider Category: Key Storage Provider
- Vink "Requests must use one of the following providers:" aan

* Vink "Microsoft Software Key Storage Provider" en "Microsoft Platform Crypto Provider" aan
* Zorg via de pijltjes dat "Microsoft Platform Crypto Provider" bovenaan komt te staan

+ Onder het tabblad 'Subject Name' geef je de volgende configuratie:

- Vink "Include e-mail name in subject name" en "E-mail name" af

+ Klik op "Apply" en OK om de wijzigingen toe te passen

* Sluit dit venster af
* Rechtsklik op 'Certificate Templates' en kies voor "New > Certificate Template to issue"

+ Kies voor de template 'VPN User Authentication' en klik op OK

> Hierdoor zal de template toegevoegd worden aan de certificate templates.

---


Video tonen/verbergen

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Configuratie user template in CA/1635172910_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
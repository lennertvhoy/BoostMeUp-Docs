---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Configuratie NPS server template in CA"
last_updated: "2026-02-05"
---

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Configuratie NPS server template in CA/1635172893_practice.png)

## 

## Configuratie NPS server template in CA

##### In deze deelopdracht configureren we de NPS server template in 'Certification Authority'.

##### 

##### 

* Log in op de server SRV-MAN-01 met de domain administrator van het netwerk AD.Training.com
* Open de console "Certification Authority"
* Klik op 'Training-DC-CA'
* Rechtsklik op 'Certificate Templates' en kies voor "Manage"
* In het venster 'Certificate Templates Console' rechtsklik je op 'RAS and IAS Server' en kies voor "Duplicate Template"

+ Onder het tabblad 'General' geef je de volgende configuratie:

- Template display name: NPS Server Authentication
- Template name: NPSServerAuthentication
- Vink "Publish certificate in Active Directory" af

+ Onder het tabblad 'Security' geef je de volgende configuratie:

- Verwijder de groep "RAS and IAS Servers"
- Voeg via "Add..."de groep "NPS Servers" toe met de permissies 'Read', 'Enroll' en 'Autoenroll'

+ Klik op "Apply" en OK om de wijzigingen toe te passen

* Sluit dit venster af
* Rechtsklik op 'Certificate Templates' en kies voor "New > Certificate Template to issue"

+ Kies voor de template 'NPS Server Authentication' en klik op OK

> Hierdoor zal de template toegevoegd worden aan de certificate templates.

* Herstart nu de server SRV-DC-01

---


Video tonen/verbergen

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Configuratie NPS server template in CA/1635172910_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
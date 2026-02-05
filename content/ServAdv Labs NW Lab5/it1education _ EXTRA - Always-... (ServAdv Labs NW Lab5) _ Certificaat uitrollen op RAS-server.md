---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Certificaat uitrollen op RAS-server"
last_updated: "2026-02-05"
---

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Certificaat uitrollen op RAS-server/1635172893_practice.png)

## 

## Certificaat uitrollen op RAS-server

##### In deze deelopdracht rollen we een certificaat uit op de server 'SRV-RAS-01'.

##### 

##### 

* Log in op de server SRV-RAS-01 met de domain administrator van het netwerk AD.Training.com
* Open de command prompt als administrator en geef het volgende commando in:
```
certlm
```

> Dit opent de console 'Certificates' op de lokale computer.

* Rechtsklik op 'Personal'  en kies voor "All Taks > Request New Certificate..."

+ Bij 'Before You Begin' klik je op Next
+ Bij 'Select Certificate Enrollment Policy' klik je op Next
+ Bij 'Request  Certificates' geef je de volgende configuratie op:

- Vink "VPN Server Authentication" aan
- Klik op "More information is required to enroll..."

* Onder 'Subject Name'  geef je de volgende configuratie op:

+ Type: Common name
+ Value: vpn.example.com (= external domain name for reaching vpn server) (klik op "Add>")

* Onder 'Alternative Name'  geef je de volgende configuratie op en klik op "Add>":

+ Type: DNS
+ Value: vpn.example.com (klik op "Add>")
+ Value: IP-adres (klik op "Add>")

* Klik op OK

- Klik op "Enroll" en "Finish"

* Ga naar 'Personal'\'Certificates'
* Rechtsklik op het certificaat en kies voor "Open"

+ Ga naar het tabblad 'Details'
+ Klik op 'Enhanced Key Usage' en controleer of er een verwijzing staat naar "IP security IKE intermediate"
+ Klik op OK om het venster te sluiten

---


Video tonen/verbergen

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Certificaat uitrollen op RAS-server/1635172910_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
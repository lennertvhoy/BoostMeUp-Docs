---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Configuratie RAS-server"
last_updated: "2026-02-05"
---

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20Configuratie%20RAS-server/1634976994_practice.png)

## 

## Configuratie RAS-server

##### In deze deelopdracht configureren we de server 'SRV-RAS-01'.

##### 

##### 

* Log in met de domain administrator op de server SRV-RAS-01
* Installeer de role 'Remote Access' via de Server Manager
* Bij 'Role Services' selecteer je de optie "DirectAccess and VPN (RAS)"

> Alles wat extra wordt geïnstalleerd laat je default staan !

* Doorloop de 'Open the Getting Started Wizard' en kies voor de optie "Deploy VPN only"
* Open de console "Routing & Remote Access"
* Rechtsklik op de servernaam 'SRV-RAS-01' en kies voor "Configure and Enable Routing and Remote Access"

+ Klik op Next
+ Selecteer "Custom Configuration" en klik op Next
+ Vink "VPN access" aan en klik op Next
+ Klik op Finish
+ Klik op "Start service"

* Rechtsklik op de servernaam 'SRV-RAS-01' en kies voor "Properties"

+ Onder 'Security' configureer je de volgende zaken en klik op OK:

- Bij 'Authentication provider' kies je voor "RADIUS Authentication"
- Klik op "Configure..." ernaast

* Klik op "Add..." om de RADIUS-server toe te voegen

+ Bij 'Server name' geef je als naam "SRV-NPS-01.AD.Training.com" op
+ Bij 'Shared secrets' klik je op "Change..." en geef je 2 maal "Azerty01" op en klik op OK

* Klik 2 maal op OK

- Bij 'Accounting provider' kies je voor "RADIUS Accounting"

+ Onder 'IPv4' configureer je de volgende zaken en klik op OK:

- Kies voor "Static address pool" en klik op "Add..."

* Voeg de pool "192.168.XXX.201 tot 192.168.XXX.250" toe

* Rechtsklik op 'Ports' en kies "Properties"

+ Configureer de volgende zaken en klik daarna op OK:

- Selecteer "WAN Miniport (SSTP)" en klik op "Configure..."

* Vink "Remote access connections..." en "Demand-dial routing..." af en klik op OK

- Selecteer "WAN Miniport (L2TP)" en klik op "Configure..."

* Vink "Remote access connections..." en "Demand-dial routing..." af en klik op OK

- Selecteer "WAN Miniport (PPTP)" en klik op "Configure..."

* Vink "Remote access connections..." en "Demand-dial routing..." af en klik op OK

* Herstart de server SRV-RAS-01

---


Video tonen/verbergen

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20Configuratie%20RAS-server/1634912178_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
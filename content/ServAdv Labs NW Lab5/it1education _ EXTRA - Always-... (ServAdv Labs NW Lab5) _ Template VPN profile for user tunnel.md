---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Template VPN profile for user tunnel"
last_updated: "2026-02-05"
---

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20Template%20VPN%20profile%20for%20user%20tunnel/1634976994_practice.png)

## 

## Template VPN profile for user tunnel

##### In deze deelopdracht configureren we een template voor het VPN-profiel voor gebruikers op de client 'CL-W10-VPN'.

##### 

##### 

* Log in met de gebruiker 'VPN-Admin' op de computer CL-W10-VPN
* Geef "VPN" in de zoekbalk in en ga naar "VPN Settings"
* Klik op "Add a VPN connection"
* Geef de volgende configuratie mee en klik op OK:

+ VPN provider: Windows (built-in)
+ Connection name: Template
+ Server name or address: vpn.example.com

* Open de 'Network Connections' applet
* Rechtsklik op 'Template' en kies voor "Properties"

+ Onder 'Security' geef je de volgende configuratie op:

- Type of VPN: IKEv2
- Data encryption: Maximum strength encryption (disconnect if server declines)
- Authentication: Microsoft: Protected EAP (PEAP) (encryption enabled)

* Klik op "Properties en geef volgende configuratie mee:

+ Connect to these servers: SRV-NPS-01.AD.Training.com
+ Trusted Root Certification Authorities: vink "TRAINING-DC-CA" aan
+ Notifications before connecting: Don't ask user to authorize new servers or trusted CAs
+ Selected Authentication Method: Smart Card or other certificate

- Klik op "Configure..." en geef volgende configuratie mee:

* When connecting: Use a certificate on this computer
* Connect to these servers: SRV-NPS-01.AD.Training.com
* Trusted Root Certification Authorities: vink "TRAINING-DC-CA" aan
* Vink "Don't prompt user to authorize new servers..." aan

- Klik op OK

+ Klik op OK

- Klik op OK

* Klik nu op 'Template' en "Connect" om de VPN-connectie tot stand te brengen

---


Video tonen/verbergen

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20Template%20VPN%20profile%20for%20user%20tunnel/1634912178_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Always On VPN Device Tunnel een eerste k"
last_updated: "2026-02-05"
---

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20Always%20On%20VPN%20Device%20Tunnel%20een%20eerste%20k/1634976994_practice.png)

## 

## Always On VPN Device Tunnel een eerste keer uittesten

##### In deze deelopdracht gaan we controleren of we automatisch via 'Always On VPN' met het netwerk AD.Training.com geconnecteerd zijn vanaf de computer CL-W10-VPN.

##### 

##### 

* Verbind de computer CL-W10-VPN met de virtuele adapter 'PHYSICAL\_NETWORK'
* Start de computer CL-W10-VPN op maar log niet in

* Login met de domain administrator van 'AD.Training.com' op de server SRV-DC-01
* Open Command Prompt en voer het volgende commando uit:
```
ping <IP-adres van CL-W10-VPN
```

> Je zou een positive reply moeten krijgen. Indien niet dan werkt de device tunnel niet!

* Login met de gebruiker VPNAdmin op de computer CL-W10-VPN
* Open de 'Network Connections' applet

> Daar moet je nu ook een adapter 'Always On VPN Device Tunnel' terugvinden.

---


Video tonen/verbergen

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20Always%20On%20VPN%20Device%20Tunnel%20een%20eerste%20k/1634912178_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
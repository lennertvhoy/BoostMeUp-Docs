---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ VM aanmaken"
last_updated: "2026-02-05"
---

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20VM%20aanmaken/1634976994_practice.png)

## 

## VM aanmaken

##### In deze deelopdracht maken we een nieuwe virtuele machine 'SRV-VPN-01' aan voor het netwerk.

##### 

##### 

## 

* Maak de volgende virtuele machine aan met de juiste configuratie:

+ Virtuele machine 1:

- Name: SRV-RAS-01
- Memory: 2048MB
- CPU: 2 vCPU
- Network 1: TRAINING\_NETWORK   (IP: 192.168.100.15 /24;  DNS: 192.168.100.2)
- Network 2: PHYSICAL\_NETWORK  (DHCP)
- Domain: AD.Training.com

+ Virtuele machine 2:

- Name: SRV-NPS-01
- Memory: 2048MB
- CPU: 2 vCPU
- Network 1: TRAINING\_NETWORK   (IP: 192.168.100.16 /24;  DNS: 192.168.100.2)
- Domain: AD.Training.com

+ Virtuele machine 3:

- Name: CL-W10-VPN
- Memory: 2048MB
- CPU: 2 vCPU
- Network 1: TRAINING\_NETWORK   (IP: 192.168.100.20 /24;  DNS: 192.168.100.2)
- Domain: AD.Training.com

* Zet de firewall uit op de servers SRV-RAS-01 en SRV-NPS-01

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20VM%20aanmaken/1634912178_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO- en certificaat-controle VPN-client"
last_updated: "2026-02-05"
---

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20GPO-%20en%20certificaat-controle%20VPN-client/1634976994_practice.png)

## 

## GPO- en certificaatcontrole VPN-client

##### In deze deelopdracht controleren we of de GPO's ingeladen zijn en het certificaat aanwezig is op de client 'CL-W10-VPN'.

##### 

##### 

* Verbind de computer CL-W10-VPN met de virtuele adapter 'PHYSICAL\_NETWORK'
* Log in met de gebruiker 'VPN-Admin' op de computer CL-W10-VPN
* Open de Command Prompt en voer de volgende zaken uit:

+ Controleer of de GPO's correct zijn ingeladen via het volgende commando:

```
gpresult /r
```

> Hier moeten de GPO's "Auto Enrollment Policy" en "Execute Powershell scripts" aanwezig zijn onder 'Applied Group Policy
> Objects'.

+ Controleer of het certificaat correct is ingeladen via het volgende commando:

```
certmgr
```

- Ga naar "Personal > Certificates" en controleer of er een certificaat aanwezig is

> Hier moet een certificaat terug te vinden zijn voor de gebruiker volgens de template 'VPN User Authentication'.

---


Video tonen/verbergen

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20GPO-%20en%20certificaat-controle%20VPN-client/1634912178_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
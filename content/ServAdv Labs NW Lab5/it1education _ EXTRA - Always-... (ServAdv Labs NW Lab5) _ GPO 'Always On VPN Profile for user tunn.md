---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO 'Always On VPN Profile for user tunn"
last_updated: "2026-02-05"
---

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO 'Always On VPN Profile for user tunn/1634976994_practice.png)

## 

## GPO 'Always On VPN Profile for user tunnel' correct ingeladen?

##### In deze deelopdracht controleren we of de GPO 'Always On VPN for user tunnel' correct is ingeladen op de client 'CL-W10-VPN'.

##### 

##### 

* Log in met de gebruiker 'VPN-Admin' op de computer CL-W10-VPN
* Geef "VPN" in de zoekbalk in en ga naar "VPN Settings"
* Rechtsklik op 'Always On VPN' en kies voor "Remove"

> Bevestig met "Remove".

* Herstart de computer
* Log in met de gebruiker 'VPN-Admin' op de computer CL-W10-VPN
* Open de Command Prompt en voer het volgende uit:

+ Controleer of de GPO's correct zijn ingeladen via het volgende commando:

```
gpresult /r
```
> Hier moeten nu ook de GPO "Set Always On VPN user tunnel" aanwezig zijn onder 'Applied Group Policy
> Objects'.

* Open de registry via het commando:
```
regedit
```

+ Controleer of de Config-Key correct is aangemaakt in de registry door te navigeren naar:
```
HKLM\System\CurrentControlSet\Services\RasMan\Config
```

- Rechtsklik op Config en kies voor "Permissions"

> Controleer de rechten van Users. Zijn deze 'FullControl' ?  
> Bekijk dit via de tab 'Advanced' onder Security !

* Geef "VPN" in de zoekbalk in en ga naar "VPN Settings"

> 'Always On VPN' moet aanwezig zijn bij de VPN-connecties.

---


Video tonen/verbergen

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO 'Always On VPN Profile for user tunn/1634912178_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
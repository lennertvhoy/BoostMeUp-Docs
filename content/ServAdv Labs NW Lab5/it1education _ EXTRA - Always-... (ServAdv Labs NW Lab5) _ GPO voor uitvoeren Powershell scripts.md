---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO voor uitvoeren Powershell scripts"
last_updated: "2026-02-05"
---

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20GPO%20voor%20uitvoeren%20Powershell%20scripts/1635578817_practice.png)

## 

## GPO voor uitvoeren Powershell scripts

##### In deze deelopdracht maken we een GPO aan zodat Powershell scripts kunnen uitgevoerd worden.

##### 

##

* Log in op de server SRV-MAN-01 met de domain administrator van het netwerk AD.Training.com
* Open de console "Group Policy Management"
* Maak een nieuwe GPO aan met de naam "Execute Powershell scripts"
* Rechtsklik op de GPO 'Execute Powershell scripts' en kies voor "Edit"

+ Ga binnen de console GPME naar het volgende pad:
```
Computer\Administrative Templates\Windows Components\Windows Powershell
```
+ Dubbelklik op 'Turn on Script Execution'

- Kies voor "Enabled" en bij options voor "Allow local scripts and remote signed scripts"
- Klik op OK

+ Ga binnen de console GPME naar het volgende pad:
```
User\Administrative Templates\Windows Components\Windows Powershell
```
+ Dubbelklik op 'Turn on Script Execution'

- Kies voor "Enabled" en bij options voor "Allow local scripts and remote signed
  scripts"
- Klik op OK

* Link de GPO 'Execute Powershell scripts' aan het
  domein

---


Video tonen/verbergen

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20GPO%20voor%20uitvoeren%20Powershell%20scripts/1635252706_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
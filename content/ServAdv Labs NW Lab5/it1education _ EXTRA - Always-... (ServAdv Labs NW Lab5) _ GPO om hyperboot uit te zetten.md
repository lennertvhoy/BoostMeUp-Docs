---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO om hyperboot uit te zetten"
last_updated: "2026-02-05"
---

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20GPO%20om%20hyperboot%20uit%20te%20zetten/1635578817_practice.png)

## 

## GPO om hyperboot uit te zetten

##### In deze deelopdracht maken we een GPO aan zodat hyperboot uitgezet wordt.

##### 

##

* Log in op de server SRV-MAN-01 met de domain administrator van het netwerk AD.Training.com
* Open de console "Group Policy Management"
* Maak een nieuwe GPO aan met de naam "Disable hyperboot"
* Rechtsklik op de GPO 'Disable hyperboot' en kies voor "Edit"

+ Ga binnen de console GPME naar het volgende pad:
```
Computer\Preferences\Registry
```
+ Rechtsklik op 'Registry' en kies voor "New > Registry Wizard"

- Bij 'Select computer' kies je voor "Local Computer" en klik op Next
- Bij 'Select any registry item...' ga je naar het volgende path:
```
HKEY_LOCAL_MACHINE\System\CrrentControlSet\Control\SessionManager
```

* Selecteer "Power" en vink "HyperbootEnabled" aan

- Klik op "Finish"

* Link de GPO 'Execute Powershell scripts' aan het
  domein

---


Video tonen/verbergen

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20GPO%20om%20hyperboot%20uit%20te%20zetten/1635252706_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO voor toevoegen VPN-Admin aan Adminis"
last_updated: "2026-02-05"
---

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20GPO%20voor%20toevoegen%20VPN-Admin%20aan%20Adminis/1635578817_practice.png)

## 

## GPO voor toevoegen VPN-Admin aan Administrators

##### In deze deelopdracht maken we een GPO aan zodat de gebruiker 'VPN-Admin' lid is van de lokale 'Administrators'-groep op de client CL-W10-VPN.

##### 

##

* Log in op de server SRV-MAN-01 met de domain administrator van het netwerk AD.Training.com
* Open de console "Group Policy Management"
* Maak een nieuwe GPO aan met de naam "Local Administrators Group GPO"
* Rechtsklik op de GPO 'Local Administrators Group GPO' en kies voor "Edit"

+ Ga binnen de console GPME naar het volgende pad:
```
Computer\Policies\Preferences\Control Panel Settings
```
+ Rechtsklik op 'Local Users and Groups' en kies voor "New > Local Group"

- Onder 'Local group' geef je de volgende configuratie op:

* Action: Update
* Group name: browse naar 'Administrators (built-in)'
* Description: Add VPN-Admin to local administrators on CL-W10-VPN
* Vink "Delete all member users" en "Delete all member groups" af
* Klik op "Add..." en voeg de gebruiker 'VPN-Admin' toe

- Onder 'Common' geef je de volgende configuratie op:

* Vink "Item-level targeting" aan en klik op "Targeting..."

+ Bij 'Targeting Editor' geef je de volgende configuratie op en klik op OK:

- Klik op 'New Item' en kies voor "Computername"
- Bij 'Computer name' geef je "CL-W10-VPN" en kies je voor "NetBIOS"

- Klik op OK

* Link de GPO 'Local Administrators Group GPO' aan
  de OU 'Workstations'

---


Video tonen/verbergen

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20GPO%20voor%20toevoegen%20VPN-Admin%20aan%20Adminis/1635252706_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
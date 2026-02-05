---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ GPO voor uitrollen certificaat"
last_updated: "2026-02-05"
---

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20GPO%20voor%20uitrollen%20certificaat/1635578817_practice.png)

## 

## GPO voor uitrollen certificaat

##### In deze deelopdracht maken we een GPO aan zodat de workstations geconfigureerd worden met het juiste certificaat voor de Always-On VPN.

##### 

##

* Log in op de server SRV-MAN-01 met de domain administrator van het netwerk AD.Training.com
* Open de console "Group Policy Management"
* Maak een nieuwe GPO aan met de naam "Auto Enrollment Policy"
* Rechtsklik op de GPO 'Auto Enrollment Policy' en kies voor "Edit"

+ Ga binnen de console GPME naar het volgende pad:
```
Computer\Policies\Windows Settings\Security Settings\Public Key Policies
```
+ Rechtsklik op 'Certificate Services Client - Auto-Enrollment' en kies voor "Properties"

- Bij 'Enrollment Policy Configuration' geef je de volgende configuraties op en klik op OK:

* Configuration Model: Enabled
* Vink "Renew Expired certificates.." en "Update certificates..." aan

+ Ga binnen de console GPME naar het volgende pad:
```
User\Policies\Windows Settings\Security Settings\Public Key Policies
```
+ Rechtsklik op 'Certificate Services Client - Auto-Enrollment' en kies voor "Properties"

- Bij 'Enrollment Policy Configuration' geef je de volgende configuraties op en klik op OK:

* Configuration Model: Enabled
* Vink "Renew Expired certificates.." en "Update certificates..." aan

+ Sluit de console GPME af

* Link de GPO 'Auto Enrollment Policy' aan het domein

---


Video tonen/verbergen

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20GPO%20voor%20uitrollen%20certificaat/1635252706_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
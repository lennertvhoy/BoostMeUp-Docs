---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Enable 'Machine Certificate Authenticati"
last_updated: "2026-02-05"
---

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Enable 'Machine Certificate Authenticati/1635578817_practice.png)

## 

## Enable 'Machine Certificate Authentication' on RAS

##### In deze deelopdracht zorgen we ervoor dat op SRV-RAS-01 de 'Machine Certification Authentication' correct werkt.

##### 

##

* Log in op de server SRV-RAS-01 met de domain administrator van het netwerk AD.Training.com
* Open 'Powershell ISE' als administrator en kopieer onderstaand script in het scriptvenster:
```
$VPNRootCertAuthority = "Training-DC-CA"
$RootCACert = (Get-ChildItem -Path cert:LocalMachine\root | Where-Object {$_.Subject -Like "*$VPNRootCertAuthority*" })
Set-VpnAuthProtocol -UserAuthProtocolAccepted Certificate, EAP -RootCertificateNameToAccept $RootCACert -PassThru
```

+ Run nu dit script

> We krijgen een warning dat de server opnieuw moet opgestart worden.

* Herstart de server SRV-RAS-01

---


Video tonen/verbergen

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ Enable 'Machine Certificate Authenticati/1635252706_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
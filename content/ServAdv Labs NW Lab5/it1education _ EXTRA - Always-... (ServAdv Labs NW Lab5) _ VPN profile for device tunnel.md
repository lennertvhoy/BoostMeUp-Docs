---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ VPN profile for device tunnel"
last_updated: "2026-02-05"
---

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ VPN profile for device tunnel/1634976994_practice.png)

## 

## VPN profile for device tunnel

##### In deze deelopdracht configureren we het VPN-profiel voor machines op de client 'CL-W10-VPN'.

##### 

##### 

* Verbind de computer CL-W10-VPN met de virtuele adapter 'TRAINING\_NETWORK'
* Download het bestand 'PsExec' naar de klascomputer en zorg dat het op de C-schijf van de computer 'CL-W10-VPN' terechtkomt
* Log in met de gebruiker 'VPN-Admin' op de computer CL-W10-VPN
* Open Command Prompt als administrator en voer het volgende commando uit:
```
cd\
PsExec.exe -i -s powershell.exe
```

> Er wordt een nieuw venster geopend.  
> Controleer nu via het commando 'whoami' als welke gebruiker je commands uitvoert.  
> Dit zou "NT AUTHORITY\SYSTEM" moeten zijn !!

* Open Notepad en kopieer onderstaand XML-bestand:
```
<VPNProfile>
  <NativeProfile>
<Servers>vpn.example.com</Servers>
<NativeProtocolType>IKEv2</NativeProtocolType>
<Authentication>
  <MachineMethod>Certificate</MachineMethod>
</Authentication>
<RoutingPolicyType>SplitTunnel</RoutingPolicyType>
 <!-- disable the addition of a class based route for the assigned IP address on the VPN interface -->
<DisableClassBasedDefaultRoute>true</DisableClassBasedDefaultRoute>
  </NativeProfile>
  <!-- use host routes(/32) to prevent routing conflicts -->
  <Route>
<Address>10.10.0.2</Address>
<PrefixSize>32</PrefixSize>
  </Route>
  <Route>
<Address>10.10.0.3</Address>
<PrefixSize>32</PrefixSize>
  </Route>
<!-- traffic filters for the routes specified above so that only this traffic can go over the device tunnel -->
  <TrafficFilter>
<RemoteAddressRanges>10.10.0.2, 10.10.0.3</RemoteAddressRanges>
  </TrafficFilter>
<!-- need to specify always on = true -->
  <AlwaysOn>true</AlwaysOn>
<!-- new node to specify that this is a device tunnel -->
 <DeviceTunnel>true</DeviceTunnel>
<!--new node to register client IP address in DNS to enable manage out -->
<RegisterDNS>true</RegisterDNS>
</VPNProfile>
```
* Bewaar dit bestand als "SampleDeviceTunnelVPNProfile.xml" op de 'Desktop' van de gebruiker
* Open 'Powershell ISE' als administrator en kopieer onderstaand script in het scriptvenster:
```
Param(
[string]$xmlFilePath,
[string]$ProfileName
)
$a = Test-Path $xmlFilePath
echo $a
$ProfileXML = Get-Content $xmlFilePath
echo $XML
$ProfileNameEscaped = $ProfileName -replace ' ', '%20'
$Version = 201606090004
$ProfileXML = $ProfileXML -replace '<', '&lt;'
$ProfileXML = $ProfileXML -replace '>', '&gt;'
$ProfileXML = $ProfileXML -replace '"', '&quot;'
$nodeCSPURI = './Vendor/MSFT/VPNv2'
$namespaceName = "root\cimv2\mdm\dmmap"
$className = "MDM_VPNv2_01"
$session = New-CimSession
try
{
$newInstance = New-Object Microsoft.Management.Infrastructure.CimInstance $className, $namespaceName
$property = [Microsoft.Management.Infrastructure.CimProperty]::Create("ParentID", "$nodeCSPURI", 'String', 'Key')
$newInstance.CimInstanceProperties.Add($property)
$property = [Microsoft.Management.Infrastructure.CimProperty]::Create("InstanceID", "$ProfileNameEscaped", 'String', 'Key')
$newInstance.CimInstanceProperties.Add($property)
$property = [Microsoft.Management.Infrastructure.CimProperty]::Create("ProfileXML", "$ProfileXML", 'String', 'Property')
$newInstance.CimInstanceProperties.Add($property)
$session.CreateInstance($namespaceName, $newInstance)
$Message = "Created $ProfileName profile."
Write-Host "$Message"
}
catch [Exception]
{
$Message = "Unable to create $ProfileName profile: $_"
Write-Host "$Message"
exit
}
$Message = "Complete."
Write-Host "$Message"
```
* Bewaar dit script als "CreateDeviceTunnelVPNProfile.ps1" op de 'Desktop' van de gebruiker
* Open Command Prompt als administrator en voer het volgende commando uit:
```
cd\
PsExec.exe -i -s powershell.exe
```

> Er wordt een nieuw venster geopend.  
> Controleer nu via het commando 'whoami' als welke gebruiker je commands uitvoert.  
> Dit zou "NT AUTHORITY\SYSTEM" moeten zijn !!

+ Voer het bovenstaande script uit in het nieuwe venster door de volgende CMD-lets in te geven:

```
# Navigate to users's folder 'Desktop'
cd ..\..\Users\VPN_Admin\Desktop
# Execute script
.\CreateDeviceTunnelVPNProfile.ps1 -xmlFilePath .\SampleDeviceTunnelVPNProfile.xml -ProfileName "Always On VPN Device Tunnel"
```

> Je moet als output te zien krijgen dat 'VPN Device Tunnel Profile' succesvol is
> aangemaakt.

---


Video tonen/verbergen

![](../../media/ServAdv Labs NW Lab5/it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ VPN profile for device tunnel/1634912178_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
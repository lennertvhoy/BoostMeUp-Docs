---
title: "it1education _ EXTRA - Always-... (ServAdv Labs NW Lab5) _ VPN profile for user tunnel"
last_updated: "2026-02-05"
---

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20VPN%20profile%20for%20user%20tunnel/1634976994_practice.png)

## 

## VPN profile for user tunnel

##### In deze deelopdracht configureren we het VPN-profiel voor gebruikers op de client 'CL-W10-VPN'.

##### 

##### 

* Verbind de computer CL-W10-VPN met de virtuele adapter 'TRAINING\_NETWORK'
* Log in met de gebruiker 'VPN-Admin' op de computer CL-W10-VPN
* Open 'Powershell ISE' als administrator en kopieer onderstaand script in het scriptvenster:
```
# Define key VPN profile parameters
$TemplateName = 'Template'
$ProfileName = 'Always On VPN'
$Servers = 'vpn.example.com'
$DnsSuffix = 'AD.Training.com'  
$DomainName = 'AD.Training.com'
$DNSServers = '192.168.XXX.2'
$TrustedNetwork = 'AD.Training.com'

# Get the EAP settings for the current profile called $TemplateName
$Connection = Get-VpnConnection -Name $TemplateName
if(!$Connection)
{
    $Message = "Unable to get $TemplateName connection profile: $_"
    Write-Host "$Message"
    exit
}
$EAPSettings= $Connection.EapConfigXmlStream.InnerXml
$ProfileNameEscaped = $ProfileName -replace ' ', '%20'

# Define ProfileXML
$ProfileXML = @("
<VPNProfile>
  <DnsSuffix>$DnsSuffix</DnsSuffix>
  <NativeProfile>
<Servers>$Servers</Servers>
<NativeProtocolType>IKEv2</NativeProtocolType>
<Authentication>
  <UserMethod>Eap</UserMethod>
  <Eap>
    <Configuration>
    $EAPSettings
    </Configuration>
  </Eap>
</Authentication>
<RoutingPolicyType>SplitTunnel</RoutingPolicyType>
  </NativeProfile>
<AlwaysOn>true</AlwaysOn>
<RememberCredentials>true</RememberCredentials>
<TrustedNetworkDetection>$TrustedNetwork</TrustedNetworkDetection>
  <DomainNameInformation>
<DomainName>$DomainName</DomainName>
<DnsServers>$DNSServers</DnsServers>
</DomainNameInformation>
</VPNProfile>
")

# Output the XML for possible use in Intune
$ProfileXML | Out-File -FilePath ($env:USERPROFILE + '\desktop\VPN_Profile.xml')

# Escape special characters in the profile (<,>,")
$ProfileXML = $ProfileXML -replace '<', '&lt;'
$ProfileXML = $ProfileXML -replace '>', '&gt;'
$ProfileXML = $ProfileXML -replace '"', '&quot;'

# Define WMI-to-CSP Bridge properties
$nodeCSPURI = "./Vendor/MSFT/VPNv2"
$namespaceName = "root\cimv2\mdm\dmmap"
$className = "MDM_VPNv2_01"
try
{

# Determine user SID for VPN profile.
    $WmiLoggedOnUsers = (Get-WmiObject Win32_LoggedOnUser).Antecedent
    If($WmiLoggedOnUsers.Count -gt 1) { 
        $WmiLoggedOnUsers = $WmiLoggedOnUsers -match "Domain=""$Domain"""
    }
$WmiUserValid = ($WmiLoggedOnUsers | Select-Object -Unique -First 1) -match 'Domain="([^"]+)",Name="([^"]+)"'
If(-not $WmiUserValid){
        Throw "Returned object is not a valid WMI string"
    }
$UserName = "$($Matches[1])\$($Matches[2])"
$ObjUser = New-Object System.Security.Principal.NTAccount($UserName)
    $Sid = $ObjUser.Translate([System.Security.Principal.SecurityIdentifier])
    $SidValue = $Sid.Value
    $Message = "User SID is $SidValue."
Write-Host "$Message"
}
catch [Exception] 
{
$Message = "Unable to get user SID. $_"
    Write-Host "$Message" 
    exit
}
try 
{
    # Define WMI session.
    $session = New-CimSession
    $options = New-Object Microsoft.Management.Infrastructure.Options.CimOperationOptions
    $options.SetCustomOption("PolicyPlatformContext_PrincipalContext_Type", "PolicyPlatform_UserContext", $false)
    $options.SetCustomOption("PolicyPlatformContext_PrincipalContext_Id", "$SidValue", $false)
}
catch {
$Message = "Unable to create new session for $ProfileName profile: $_"
    Write-Host $Message
    exit
}
try
{
    #Detect and delete previous VPN profile.
    $deleteInstances = $session.EnumerateInstances($namespaceName, $className, $options)
foreach ($deleteInstance in $deleteInstances)
    {
        $InstanceId = $deleteInstance.InstanceID
        if ("$InstanceId" -eq "$ProfileNameEscaped")
        {
            $session.DeleteInstance($namespaceName, $deleteInstance, $options)
            $Message = "Removed $ProfileName profile $InstanceId" 
            Write-Host "$Message"
        }
        else 
        {
            $Message = "Ignoring existing VPN profile $InstanceId"
            Write-Host "$Message"
        }
    }
}
catch [Exception]
{
    $Message = "Unable to remove existing outdated instance(s) of $ProfileName profile: $_"
    Write-Host $Message
    exit
}
try
{
    # Create the VPN profile.
    $newInstance = New-Object Microsoft.Management.Infrastructure.CimInstance $className, $namespaceName
    $property = [Microsoft.Management.Infrastructure.CimProperty]::Create("ParentID", "$nodeCSPURI", "String", "Key")
    $newInstance.CimInstanceProperties.Add($property)
    $property = [Microsoft.Management.Infrastructure.CimProperty]::Create("InstanceID", "$ProfileNameEscaped", "String", "Key")
    $newInstance.CimInstanceProperties.Add($property)
    $property = [Microsoft.Management.Infrastructure.CimProperty]::Create("ProfileXML", "$ProfileXML", "String", "Property")
    $newInstance.CimInstanceProperties.Add($property)
    $session.CreateInstance($namespaceName, $newInstance, $options)
$Message = "Created $ProfileName profile."
    Write-Host "$Message"
}
catch [Exception]
{
$Message = "Unable to create $ProfileName profile: $_"
    Write-Host "$Message"
    exit
}
$Message = "Script Complete"
Write-Host "$Message"
```
* Bewaar dit script op de 'Desktop' van de gebruiker
* Open Powershell als administrator
* Voer het bovenstaande script uit door de volgende CMD-lets in te geven:
```
# Navigate to users's folder 'Desktop'
cd ..\..\Users\VPN_Admin\Desktop
# Execute script
.\makeProfile.ps1
```

> Je moet als output te zien krijgen dat 'VPN\_Profile.xml' en 'VPN\_Profile.ps1' succesvol zijn aangemaakt.

* Voer nu het script 'VPN\_Profile.ps1' uit door het volgende CMD-let in te geven:
```
.\VPN_Profile.ps1
```

> Je moet als output te zien krijgen dat 'Always On VPN profile' is aangemaakt en het script succesvol is
> uitgevoerd.

---


Video tonen/verbergen

![](../../media/ServAdv%20Labs%20NW%20Lab5/it1education%20_%20EXTRA%20-%20Always-...%20%28ServAdv%20Labs%20NW%20Lab5%29%20_%20VPN%20profile%20for%20user%20tunnel/1634912178_suru-qfor.png)

### Is alles gelukt?

## 

Ga dan verder naar het volgende onderdeel.
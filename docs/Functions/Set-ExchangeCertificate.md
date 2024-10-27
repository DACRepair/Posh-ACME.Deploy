---
external help file: Posh-ACME.Deploy-help.xml
Module Name: Posh-ACME.Deploy
online version: https://docs.dvolve.net/Posh-ACME.Deploy/v2/Functions/Set-ExchangeCertificate/
schema: 2.0.0
---

# Set-ExchangeCertificate

## Synopsis

Configure Exchange service to use the specified certificate.

## Syntax

```powershell
Set-ExchangeCertificate [[-CertThumbprint] <String>] [[-PfxFile] <String>] [[-PfxPass] <SecureString>]
 [-ExchangeServices <String[]>] [-RemoveOldCert] [<CommonParameters>]
```

## Description

Intended to be used with the output from Posh-ACME's New-PACertificate or Submit-Renewal.

## Examples

### EXAMPLE 1
```
New-PACertificate site1.example.com | Set-ExchangeCertificate
```

Create a new certificate and configure it for Exchange on this system.

### EXAMPLE 2
```
Submit-Renewal site1.example.com | Set-ExchangeCertificate
```

Renew a certificate and configure it for Exchange on this system.

## Parameters

### -CertThumbprint
Thumbprint/Fingerprint for the certificate to configure.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Thumbprint

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExchangeServices
The name of the Exchange services to configure.
Defaults to 'IIS,SMTP'.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: @('IMAP', 'POP', 'IIS','SMTP')
Accept pipeline input: False
Accept wildcard characters: False
```

### -PfxFile
Path to a PFX containing a certificate and private key.
Not required if the certificate is already in the local system's Personal certificate store.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PfxPass
The export password for the specified PfxFile parameter.
Not required if the Pfx does not require an export password.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemoveOldCert
If specified, the old certificate will be deleted from the local system's Personal certificate store.
Ignored if the old certificate has already been removed or otherwise can't be found.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Related Links
---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online
schema: 2.0.0
---

# Get-TextMessagingAccount

## SYNOPSIS
!!! Exchange Server 2010

Use the Get-TextMessagingAccount cmdlet to return a user's short messaging service (SMS) settings.

!!! Exchange Server 2013, Exchange Server 2016, Exchange Online

This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the Get-TextMessagingAccount cmdlet to return a user's Short Message Service (SMS) settings.

For information about the parameter sets in the Syntax section below, see Exchange cmdlet syntax (https://technet.microsoft.com/library/bb123552.aspx).

## SYNTAX

```
Get-TextMessagingAccount [-Identity] <MailboxIdParameter> [-Credential <PSCredential>]
 [-DomainController <Fqdn>] [-ReadFromDomainController] [-ResultSize <Unlimited>] [<CommonParameters>]
```

## DESCRIPTION
!!! Exchange Server 2010

The Get-TextMessagingAccount cmdlet gets the SMS settings for a particular user. These settings include whether Microsoft Exchange ActiveSync is enabled, the user's country or region ID, mobile operator ID, service provider ID, and notification phone number.

You need to be assigned permissions before you can run this cmdlet. Although all parameters for this cmdlet are listed in this topic, you may not have access to some parameters if they're not included in the permissions assigned to you. To see what permissions you need, see the "Text messaging settings" entry in the Client Access Permissions topic.

!!! Exchange Server 2013

The Get-TextMessagingAccount cmdlet displays the SMS settings for a specific user. These settings include whether Microsoft Exchange ActiveSync is enabled, the user's country or region ID, mobile operator ID, service provider ID, and notification phone number.

You need to be assigned permissions before you can run this cmdlet. Although all parameters for this cmdlet are listed in this topic, you may not have access to some parameters if they're not included in the permissions assigned to you. To see what permissions you need, see the "Text messaging settings" entry in the Clients and mobile devices permissions topic.

!!! Exchange Server 2016, Exchange Online

The Get-TextMessagingAccount cmdlet displays the SMS settings for a specific user. These settings include whether Exchange ActiveSync is enabled, the user's country or region ID, mobile operator ID, service provider ID, and notification phone number.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see Find the permissions required to run any Exchange cmdlet (https://technet.microsoft.com/library/mt432940.aspx).

## EXAMPLES

### Example 1 -------------------------- (Exchange Server 2010)
```
Get-TextMessagingAccount -Identity "TonySmith" -DomainController server.contoso.com
```

This example returns the text messaging settings for Tony Smith's mailbox using his alias.

### Example 1 -------------------------- (Exchange Server 2013)
```
Get-TextMessagingAccount -Identity "TonySmith" -DomainController server.contoso.com
```

This example returns the text messaging settings for Tony Smith's mailbox using his alias.

### Example 1 -------------------------- (Exchange Server 2016)
```
Get-TextMessagingAccount -Identity tony@contoso.com
```

This example returns the text messaging settings for Tony's mailbox.

### Example 1 -------------------------- (Exchange Online)
```
Get-TextMessagingAccount -Identity tony@contoso.com
```

This example returns the text messaging settings for Tony's mailbox.

### Example 2 -------------------------- (Exchange Server 2010)
```
Get-TextMessagingAccount -Identity "contoso\tonysmith" -DomainController DC1.contoso.com
```

This example returns the text messaging settings for Tony Smith's mailbox using his domain and username.

### Example 2 -------------------------- (Exchange Server 2013)
```
Get-TextMessagingAccount -Identity "contoso\tonysmith" -DomainController DC1.contoso.com
```

This example returns the text messaging settings for Tony Smith's mailbox using his domain and username.

### Example 3 -------------------------- (Exchange Server 2010)
```
Get-TextMessagingAccount -Identity "tony@contoso.com" -DomainController gc.contoso.com
```

This example returns the text messaging settings for Tony Smith's mailbox using his e-mail address.

### Example 3 -------------------------- (Exchange Server 2013)
```
Get-TextMessagingAccount -Identity "tony@contoso.com" -DomainController gc.contoso.com
```

This example returns the text messaging settings for Tony Smith's mailbox using his email address.

## PARAMETERS

### -Identity
!!! Exchange Server 2010, Exchange Server 2013

The Identity parameter specifies the identity of the mailbox.



!!! Exchange Server 2016, Exchange Online

The Identity parameter specifies the mailbox that you want to view. You can use any value that uniquely identifies the mailbox.

For example:

- Name

- Display name

- Alias

- Distinguished name (DN)

- Canonical DN

- \<domain name\>\\\<account name\>

- Email address

- GUID

- LegacyExchangeDN

- SamAccountName

- User ID or user principal name (UPN)



```yaml
Type: MailboxIdParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -Credential
!!! Exchange Server 2010

The Credential parameter specifies the logon credentials of the user.



!!! Exchange Server 2013

This parameter requires the creation and passing of a credential object. This credential object is created by using the Get-Credential cmdlet. For more information, see Get-Credential (https://go.microsoft.com/fwlink/p/?linkId=142122).



!!! Exchange Server 2016, Exchange Online

This parameter requires you to create a credentials object by using the Get-Credential cmdlet. For more information, see Get-Credential (https://go.microsoft.com/fwlink/p/?linkId=142122).



```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainController
!!! Exchange Server 2010

The DomainController parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, dc01.contoso.com.



!!! Exchange Server 2013, Exchange Server 2016, Exchange Online

This parameter is available only in on-premises Exchange.

The DomainController parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, dc01.contoso.com.



```yaml
Type: Fqdn
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReadFromDomainController
!!! Exchange Server 2010

The ReadFromDomainController parameter specifies whether the cmdlet should return data from the domain controller.



!!! Exchange Server 2013, Exchange Server 2016, Exchange Online

The ReadFromDomainController switch specifies that information should be read from a domain controller in the user's domain. If you run the command Set-AdServerSettings -ViewEntireForest $true to include all objects in the forest and you don't use the ReadFromDomainController switch, it's possible that information will be read from a global catalog that has outdated information. When you use the ReadFromDomainController switch, multiple reads might be necessary to get the information. You don't have to specify a value with this switch.

By default, the recipient scope is set to the domain that hosts your Exchange servers.



```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultSize
!!! Exchange Server 2010

The ResultSize parameter specifies the amount of data returned.



!!! Exchange Server 2013, Exchange Server 2016, Exchange Online

The ResultSize parameter specifies the maximum number of results to return. If you want to return all requests that match the query, use unlimited for the value of this parameter. The default value is 1000.



```yaml
Type: Unlimited
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

###  
To see the input types that this cmdlet accepts, see Cmdlet Input and Output Types (https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.

## OUTPUTS

###  
To see the return types, which are also known as output types, that this cmdlet accepts, see Cmdlet Input and Output Types (https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.

## NOTES

## RELATED LINKS

[Online Version](https://technet.microsoft.com/library/2d692e94-1b64-4bdf-b486-31f11110fb31.aspx)


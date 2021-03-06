---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online
schema: 2.0.0
---

# Test-MAPIConnectivity

## SYNOPSIS
!!! Exchange Server 2010

Use the Test-MapiConnectivity cmdlet to verify server functionality by logging on to the mailbox that you specify. If you don't specify a mailbox, the cmdlet logs on to the SystemMailbox on the database that you specify.

!!! Exchange Server 2013, Exchange Server 2016, Exchange Online

This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the Test-MapiConnectivity cmdlet to verify server functionality by logging on to the mailbox that you specify. If you don't specify a mailbox, the cmdlet logs on to the SystemMailbox on the database that you specify.

For information about the parameter sets in the Syntax section below, see Exchange cmdlet syntax (https://technet.microsoft.com/library/bb123552.aspx).

## SYNTAX

### Set2
```
Test-MAPIConnectivity -Database <DatabaseIdParameter> [-ActiveDirectoryTimeout <Int32>]
 [-AllConnectionsTimeout <Int32>] [-Confirm] [-DomainController <Fqdn>] [-MonitoringContext <$true | $false>]
 [-PerConnectionTimeout <Int32>] [-WhatIf] [-CopyOnServer <ServerIdParameter>] [<CommonParameters>]
```

### Set3
```
Test-MAPIConnectivity [-Identity] <MailboxIdParameter> [-ActiveDirectoryTimeout <Int32>]
 [-AllConnectionsTimeout <Int32>] [-Archive] [-Confirm] [-DomainController <Fqdn>]
 [-MonitoringContext <$true | $false>] [-PerConnectionTimeout <Int32>] [-WhatIf]
 [-CopyOnServer <ServerIdParameter>] [<CommonParameters>]
```

### Set1
```
Test-MAPIConnectivity [-ActiveDirectoryTimeout <Int32>] [-AllConnectionsTimeout <Int32>] [-Confirm]
 [-DomainController <Fqdn>] [-MonitoringContext <$true | $false>] [-PerConnectionTimeout <Int32>]
 [-Server <ServerIdParameter>] [-WhatIf] [-IncludePassive] [<CommonParameters>]
```

## DESCRIPTION
!!! Exchange Server 2010

The Test-MapiConnectivity cmdlet verifies server functionality. This cmdlet logs on to the mailbox that you specify (or to the SystemMailbox if you don't specify the Identity parameter) and retrieves a list of items in the Inbox. Logging on to the mailbox tests two critical protocols used when a client connects to a Mailbox server: MAPI and LDAP. During authentication, the Test-MapiConnectivity cmdlet indirectly verifies that the MAPI server, Exchange store, and Directory Service Access (DSAccess) are working.

The cmdlet logs on to the mailbox that you specify using the credentials of the account with which you are logged on to the local computer. After a successful authentication, the Test-MapiConnectivity cmdlet accesses the mailbox to verify that the database is working. If a successful connection to a mailbox is made, the cmdlet also determines the time that the logon attempt occurred.

There are three distinct parameters that you can use with the command: Database, Identity, and Server:

- The Database parameter takes a database identity and tests the ability to log on to the system mailbox on the specified database.

- The Identity parameter takes a mailbox identity and tests the ability to log on to a specific mailbox.

- The Server parameter takes a server identity and tests the ability to log on to each system mailbox on the specified server.

You need to be assigned permissions before you can run this cmdlet. Although all parameters for this cmdlet are listed in this topic, you may not have access to some parameters if they're not included in the permissions assigned to you. To see what permissions you need, see the "MAPI connectivity" entry in the Mailbox Permissions topic.

!!! Exchange Server 2013

The Test-MapiConnectivity cmdlet verifies server functionality. This cmdlet logs on to the mailbox that you specify (or to the SystemMailbox if you don't specify the Identity parameter) and retrieves a list of items in the Inbox. Logging on to the mailbox tests two critical protocols used when a client connects to a Mailbox server: MAPI and LDAP. During authentication, the Test-MapiConnectivity cmdlet indirectly verifies that the MAPI server, Exchange store, and Directory Service Access (DSAccess) are working.

The cmdlet logs on to the mailbox that you specify using the credentials of the account with which you're logged on to the local computer. After a successful authentication, the Test-MapiConnectivity cmdlet accesses the mailbox to verify that the database is working. If a successful connection to a mailbox is made, the cmdlet also determines the time that the logon attempt occurred.

There are three distinct parameters that you can use with the command: Database, Identity, and Server:

- The Database parameter takes a database identity and tests the ability to log on to the system mailbox on the specified database.

- The Identity parameter takes a mailbox identity and tests the ability to log on to a specific mailbox.

- The Server parameter takes a server identity and tests the ability to log on to each system mailbox on the specified server.

You need to be assigned permissions before you can run this cmdlet. Although all parameters for this cmdlet are listed in this topic, you may not have access to some parameters if they're not included in the permissions assigned to you. To see what permissions you need, see the "MAPI connectivity" entry in the Recipients Permissions topic.

!!! Exchange Server 2016, Exchange Online

The Test-MapiConnectivity cmdlet verifies server functionality. This cmdlet logs on to the mailbox that you specify (or to the SystemMailbox if you don't specify the Identity parameter) and retrieves a list of items in the Inbox. Logging on to the mailbox tests two critical protocols used when a client connects to a Mailbox server: MAPI and LDAP. During authentication, the Test-MapiConnectivity cmdlet indirectly verifies that the MAPI server, Exchange store, and Directory Service Access (DSAccess) are working.

The cmdlet logs on to the mailbox that you specify using the credentials of the account with which you're logged on to the local computer. After a successful authentication, the Test-MapiConnectivity cmdlet accesses the mailbox to verify that the database is working. If a successful connection to a mailbox is made, the cmdlet also determines the time that the logon attempt occurred.

There are three distinct parameters that you can use with the command: Database, Identity, and Server:

- The Database parameter takes a database identity and tests the ability to log on to the system mailbox on the specified database.

- The Identity parameter takes a mailbox identity and tests the ability to log on to a specific mailbox.

- The Server parameter takes a server identity and tests the ability to log on to each system mailbox on the specified server.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see Find the permissions required to run any Exchange cmdlet (https://technet.microsoft.com/library/mt432940.aspx).

## EXAMPLES

### Example 1 -------------------------- (Exchange Server 2010)
```
Test-MapiConnectivity -Server "Server01"
```

This example tests connectivity to the server Server01.

### Example 1 -------------------------- (Exchange Server 2013)
```
Test-MapiConnectivity -Server "Server01"
```

This example tests connectivity to the server Server01.

### Example 1 -------------------------- (Exchange Server 2016)
```
Test-MapiConnectivity -Server "Server01"
```

This example tests connectivity to the server Server01.

### Example 1 -------------------------- (Exchange Online)
```
Test-MapiConnectivity -Server "Server01"
```

This example tests connectivity to the server Server01.

### Example 2 -------------------------- (Exchange Server 2010)
```
Test-MapiConnectivity -Identity "midwest\john"
```

This example tests connectivity to a mailbox, specified as a domain name and user name.

### Example 2 -------------------------- (Exchange Server 2013)
```
Test-MapiConnectivity -Identity "midwest\john"
```

This example tests connectivity to a mailbox, specified as a domain name and user name.

### Example 2 -------------------------- (Exchange Server 2016)
```
Test-MapiConnectivity -Identity "midwest\john"
```

This example tests connectivity to a mailbox, specified as a domain name and user name.

### Example 2 -------------------------- (Exchange Online)
```
Test-MapiConnectivity -Identity "midwest\john"
```

This example tests connectivity to a mailbox, specified as a domain name and user name.

## PARAMETERS

### -Database
!!! Exchange Server 2010

The Database parameter specifies the database on which to test the connectivity to the system mailbox. If you don't specify this parameter or the Identity parameter, the command tests the SystemMailbox on each active database on the server that you specify, or on the local server if you don't specify the Server parameter.



!!! Exchange Server 2013, Exchange Server 2016, Exchange Online

This parameter is available only in on-premises Exchange.

The Database parameter specifies the database on which to test the connectivity to the system mailbox. If you don't specify this parameter or the Identity parameter, the command tests the SystemMailbox on each active database on the server that you specify, or on the local server if you don't specify the Server parameter.



```yaml
Type: DatabaseIdParameter
Parameter Sets: Set2
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online

Required: True
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -Identity
!!! Exchange Server 2010

The Identity parameter specifies a mailbox to test. You can use the following values:

- GUID

- Distinguished name (DN)

- Domain\\Account

- User principal name (UPN)

- Legacy Exchange DN

- SMTP address

- Alias

- This parameter accepts pipeline input from the Get-Mailbox or Get-Recipient cmdlet. If an object is piped from the Get-Mailbox cmdlet or Get-Recipient cmdlet, this parameter isn't required.

- If you don't specify this parameter, the cmdlet tests the SystemMailbox on the database that you specify.



!!! Exchange Server 2013, Exchange Server 2016, Exchange Online

The Identity parameter specifies a mailbox to test. You can use the following values:

- GUID

- Distinguished name (DN)

- Domain\\Account

- User principal name (UPN)

- Legacy Exchange DN

- SMTP address

- Alias

This parameter accepts pipeline input from the Get-Mailbox or Get-Recipient cmdlet. If an object is piped from the Get-Mailbox cmdlet or Get-Recipient cmdlet, this parameter isn't required.

If you don't specify this parameter, the cmdlet tests the SystemMailbox on the database that you specify.



```yaml
Type: MailboxIdParameter
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -ActiveDirectoryTimeout
!!! Exchange Server 2010

The ActiveDirectoryTimeout parameter specifies the amount of time, in seconds, allowed for each Active Directory operation to complete before the operation times out. The default value is 15 seconds.



!!! Exchange Server 2013, Exchange Server 2016, Exchange Online

This parameter is available only in on-premises Exchange.

The ActiveDirectoryTimeout parameter specifies the amount of time, in seconds, allowed for each Active Directory operation to complete before the operation times out. The default value is 15 seconds.



```yaml
Type: Int32
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllConnectionsTimeout
!!! Exchange Server 2010

The AllConnectionsTimeout parameter specifies the amount of time, in seconds, allowed for all connections to complete before the cmdlet times out. The time-out countdown doesn't begin until all information necessary to perform the connections is gathered from Active Directory.The default value is 90 seconds.



!!! Exchange Server 2013, Exchange Server 2016, Exchange Online

This parameter is available only in on-premises Exchange.

The AllConnectionsTimeout parameter specifies the amount of time, in seconds, allowed for all connections to complete before the cmdlet times out. The time-out countdown doesn't begin until all information necessary to perform the connections is gathered from Active Directory.The default value is 90 seconds.



```yaml
Type: Int32
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Archive
!!! Exchange Server 2010

The Archive parameter specifies to test the MAPI connectivity of the personal archive associated with the specified mailbox. If you don't specify this parameter, only the primary mailbox is tested.



!!! Exchange Server 2013, Exchange Server 2016, Exchange Online

The Archive parameter specifies whether to test the MAPI connectivity of the personal archive associated with the specified mailbox. If you don't specify this parameter, only the primary mailbox is tested.



```yaml
Type: SwitchParameter
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
!!! Exchange Server 2010, Exchange Server 2013

The Confirm switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding.

- Destructive cmdlets (for example, Remove-* cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: -Confirm:$false.

- Most other cmdlets (for example, New-* and Set-* cmdlets) don't have a built-in pause. For these cmdlets, specifying the Confirm switch without a value introduces a pause that forces you acknowledge the command before proceeding.



!!! Exchange Server 2016, Exchange Online

The Confirm switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding.

- Destructive cmdlets (for example, Remove-\* cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: -Confirm:$false.

- Most other cmdlets (for example, New-\* and Set-\* cmdlets) don't have a built-in pause. For these cmdlets, specifying the Confirm switch without a value introduces a pause that forces you acknowledge the command before proceeding.



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

### -MonitoringContext
!!! Exchange Server 2010

The MonitoringContext parameter specifies whether the results of the command include monitoring events and performance counters. The two possible values for this parameter are $true or $false. If you specify $true, the results include monitoring events and performance counters, in addition to the information about the MAPI transaction.



!!! Exchange Server 2013

This parameter is available only in on-premises Exchange.

The MonitoringContext parameter includes or excludes the associated monitoring events and performance counters in the results. Valid input for this parameter is $true or $false. The default value is $false. If you specify the value $true, the monitoring events and performance counters are included in the command results. Typically, you include the monitoring events and performance counters in the results when the output is passed to Microsoft System Center Operations Manager 2007 or System Center 2012 - Operations Manager.



!!! Exchange Server 2016, Exchange Online

This parameter is available only in on-premises Exchange.

The MonitoringContext parameter specifies whether to include the associated monitoring events and performance counters in the results. Valid values for this parameter are $true or $false. The default value is $false. If you specify the value $true, the monitoring events and performance counters are included in the command results. Typically, you include the monitoring events and performance counters in the results when the output is passed to MicrosoftSystem Center Operations Manager (SCOM).



```yaml
Type: $true | $false
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PerConnectionTimeout
!!! Exchange Server 2010

The PerConnectionTimeout parameter specifies the amount of time, in seconds, allowed for each connection to complete before the connection times out. The default value is 10 seconds.



!!! Exchange Server 2013, Exchange Server 2016, Exchange Online

This parameter is available only in on-premises Exchange.

The PerConnectionTimeout parameter specifies the amount of time, in seconds, allowed for each connection to complete before the connection times out. The default value is 10 seconds.



```yaml
Type: Int32
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
!!! Exchange Server 2010

The Server parameter specifies the server on which you will test the MAPI connectivity. The command tests the MAPI connectivity to each system mailbox hosted on active databases on the specified server.

If you don't specify this parameter, the command tests the mailbox on the local server.



!!! Exchange Server 2013, Exchange Server 2016, Exchange Online

This parameter is available only in on-premises Exchange.

The Server parameter specifies the server on which you will test the MAPI connectivity. The command tests the MAPI connectivity to each system mailbox hosted on active databases on the specified server.

If you don't specify this parameter, the command tests the mailbox on the local server.



```yaml
Type: ServerIdParameter
Parameter Sets: Set1
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Online

Required: False
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -WhatIf
The WhatIf switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch.

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

### -CopyOnServer
This parameter is available only in on-premises Exchange.

The CopyOnServer parameter is used to test MAPI connectivity to a specific database copy on the servers specified with the Server parameter.

```yaml
Type: ServerIdParameter
Parameter Sets: Set2, Set3
Aliases:
Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludePassive
This parameter is available only in on-premises Exchange.

Without the IncludePassive parameter, the cmdlet tests MAPI connectivity from active database copies only. Using the IncludePassive parameter, you can have the cmdlet test MAPI connectivity from all active and passive database copies.

```yaml
Type: SwitchParameter
Parameter Sets: Set1
Aliases:
Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Online

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

[Online Version](https://technet.microsoft.com/library/89c5b599-0a92-4857-880c-aea5f1e6c8bd.aspx)


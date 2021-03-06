---
applicable: Exchange Server 2010
schema: 2.0.0
---

# get-ManagedFolderMailboxPolicy

## SYNOPSIS
Use the Get-ManagedFolderMailboxPolicy cmdlet to return all attributes of one or more managed folder mailbox policies.

## SYNTAX

```
get-ManagedFolderMailboxPolicy [[-Identity] <MailboxPolicyIdParameter>] [-DomainController <Fqdn>]
 [-Organization <OrganizationIdParameter>] [<CommonParameters>]
```

## DESCRIPTION
A managed folder mailbox policy is a logical grouping of one or more managed folders. Policies are applied to mailboxes. The Get-ManagedFolderMailboxPolicy cmdlet lists one or more managed folder mailbox policies created in the Microsoft Exchange Server 2010 organization. All policies can be listed.

You need to be assigned permissions before you can run this cmdlet. Although all parameters for this cmdlet are listed in this topic, you may not have access to some parameters if they're not included in the permissions assigned to you. To see what permissions you need, see the "Messaging records management" entry in the Messaging Policy and Compliance Permissions topic.

## EXAMPLES

### Example 1 -------------------------- (Exchange Server 2010)
```
Get-ManagedFolderMailboxPolicy "PM Storage Template"
```

This example returns all the attributes of the managed folder mailbox policy PM Storage Template.


The Identity parameter is a positional parameter. Positional parameters can be used without the label (Identity). For more information about positional parameters, see Parameters.

## PARAMETERS

### -DomainController
The DomainController parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, dc01.contoso.com.

```yaml
Type: Fqdn
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
The Identity parameter specifies the name, distinguished name (DN), or GUID of the managed folder mailbox policy.

```yaml
Type: MailboxPolicyIdParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010

Required: False
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -Organization
This parameter is available for multi-tenant deployments. It isn't available for on-premises deployments. For more information about multi-tenant deployments, see Multi-Tenant Support.

The Organization parameter specifies the organization in which you'll perform this action. This parameter doesn't accept wildcard characters, and you must use the exact name of the organization.

```yaml
Type: OrganizationIdParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010

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

[Online Version](https://technet.microsoft.com/library/3a151aa9-ff32-46a9-a3b8-8fbd043cedc3.aspx)


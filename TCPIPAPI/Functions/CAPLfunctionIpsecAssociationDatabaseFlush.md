[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpsecAssociationDatabaseFlush.md)

**CAPL Functions** » **TCP/IP API** » **ipsecAssociationDatabaseFlush**

# ipsecAssociationDatabaseFlush

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

**Note**  
The function is dependent on the selected stack.  
It is not possible to modify the security association database of the operating system TCP/IP stack.

## Function Syntax

```plaintext
long ipsecAssociationDatabaseFlush(char[] protocol);
```

## Description

With this function, it is possible to manually delete all security associations of the same protocol type from the security association database of the current network stack.

## Parameters

- **protocol**: The Ipsec protocol of the security association. The following values are possible:
  - **UNSPEC**: 0
  - **ESP**: 1
  - **AH**: 2

## Return Values

- **0**: Success
- **-1**: Failed

## Example

```plaintext
void CleanSecurityAssociationDatabase()
{
  // clean the security association database
  IPsecAssociationDatabaseFlush("ah");
  IPsecAssociationDatabaseFlush("esp");
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

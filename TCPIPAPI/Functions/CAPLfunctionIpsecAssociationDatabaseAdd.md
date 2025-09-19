[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpsecAssociationDatabaseAdd.md)

**CAPL Functions** » **TCP/IP API** » **ipsecAssociationDatabaseAdd**

# ipsecAssociationDatabaseAdd

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
The function is dependent on the selected stack.  
It is not possible to modify the security association database of the operating system TCP/IP stack.

## Function Syntax

```plaintext
long ipsecAssociationDatabaseAdd(long association);
```

## Description

With this function it is possible to manually add a security association to the security association database of the current network stack.

A security association record can be created with [ipsecAssociationInit](CAPLfunctionIpsecAssociationInit.md) or with [ipsecAssociationDatabaseGetSpi](CAPLfunctionIpsecAssociationDatabaseGetSpi.md).

## Parameters

- **association**: Handle to a security association record object.

## Return Values

- **0**: Success
- **-1**: Failed

## Example

```plaintext
on start
{
  long association;

  // create and init a security association record
  association = ipsecAssociationInit(ip_Endpoint(192.168.1.1), ip_Endpoint(192.168.1.10), "ah", "any", 30000);

  // add the security association to the security association database
  ipsecAssociationDatabaseAdd(association);

  // release the association record object when it isn't needed anymore
  ipsecAssociationRelease(association);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

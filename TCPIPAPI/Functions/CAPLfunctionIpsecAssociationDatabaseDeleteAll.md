[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpsecAssociationDatabaseDeleteAll.md)

**CAPL Functions** » **TCP/IP API** » **ipsecAssociationDatabaseDeleteAll**

# ipsecAssociationDatabaseDeleteAll

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- The function is dependent on the selected stack.
- It is not possible to modify the security association database of the operating system TCP/IP stack.

## Function Syntax

```plaintext
long ipsecAssociationDatabaseDeleteAll(IP_Endpoint source, IP_Endpoint destination, char[] protocol, char[] mode);
```

## Description

With this function, it is possible to manually delete all security associations independent of their spi from the security association database of the current network stack.

## Parameters

- **source**: Source endpoint of the security association.
- **destination**: Destination endpoint of the security association.
- **protocol**: The Ipsec protocol of the security association. The following values are possible:
  - **UNSPEC**: 0
  - **ESP**: 1
  - **AH**: 2
- **mode**: The IPsec mode of the security association. The following values are possible:
  - **ANY**: 0
  - **TRANSPORT**: 1
  - **TUNNEL**: 2

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

  // release the association object when it isn't needed anymore
  ipsecAssociationRelease(association);
}

on stopMeasurement
{
  // delete the security association from the security association database
  ipsecAssociationDatabaseDeleteAll(ip_Endpoint(192.168.1.1), ip_Endpoint(192.168.1.10), "ah", "any");
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

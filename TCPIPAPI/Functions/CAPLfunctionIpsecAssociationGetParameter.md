[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpsecAssociationGetParameter.md)

**CAPL Functions** » **TCP/IP API** » **ipsecAssociationGetParameter**

# ipsecAssociationGetParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
The function is dependent on the selected stack. It is not possible to modify the security association database of the operating system TCP/IP stack.

## Function Syntax

- `long ipsecAssociationGetParameter(long association, char[] parameter, char[] value);  // form 1`
- `long ipsecAssociationGetParameter(long association, char[] parameter, byte[] value);  // form 2`
- `long ipsecAssociationGetParameter(long association, char[] parameter, IP_Endpoint value); // form 3`
- `long ipsecAssociationGetParameter(long association, char[] parameter, dword value);  // form 4`

## Description

Get the value of a parameter from a IPsec security association record. A security association record can be created with [ipsecAssociationInit](CAPLfunctionIpsecAssociationInit.md) or with [ipsecAssociationDatabaseGetSpi](CAPLfunctionIpsecAssociationDatabaseGetSpi.md).

## Parameters

- **association**: Handle to a security association record object.
- **parameter**: Name of the parameter. Possible values are:
  - **source**: Source endpoint of the security association.
  - **destination**: Destination endpoint of the security association.
  - **protocol**: Returns the protocol of the security association. Possible values are:
    - **UNSPEC**: 0
    - **ESP**: 1
    - **AH**: 2
  - **mode**: Returns the mode of the security association. Possible values are:
    - **ANY**: 0
    - **TRANSPORT**: 1
    - **TUNNEL**: 2
  - **spi**: Returns the security parameter index of the security association.
  - **espalgorithm**: Returns the used esp algorithm. Possible values are:
    - NONE
    - AES
    - AES128
    - AES192
    - AES256
  - **espkey**: Returns the key of the esp algorithm.
  - **ahalgorithm**: Returns the used esp algorithm. Possible values are:
    - NULL
    - SHA2_512
    - SHA512
    - AES192GMAC
    - AES128GMAC
    - SHA256
    - SHA2_256
    - SHA2_384
    - SHA384
    - SHA
    - SHA1
    - AES256GMAC
    - AESCMAC
    - SHA1_160
    - NONE
  - **ahkey**: Returns the key of the esp algorithm.
  - **windowSize**: Replay window size in byte.
  - **esn**:
    - 0: extended sequence number disabled
    - 1: extended sequence number enabled
- **value**: The returned value of the parameter.

## Return Values

### Form 1-2

- **>0**: Success: count of characters/bytes returned.
- **-1**: Failed

### Form 3-4

- **0**: Success
- **-1**: Failed

## Example

```plaintext
on start
{
  long association;

  // create and init a security association record
  association = ipsecAssociationInit(ip_Endpoint(192.168.1.1), ip_Endpoint(192.168.1.10), "ah", "any", 30000);

  // print the parameter of the security association
  PrintSecurityAssociationAddressParameter(association, "source");
  PrintSecurityAssociationAddressParameter(association, "destination");
  PrintSecurityAssociationStringParameter(association, "protocol");
  PrintSecurityAssociationStringParameter(association, "mode");
  PrintSecurityAssociationNumberParameter(association, "spi");
  PrintSecurityAssociationStringParameter(association, "espAlgorithm");
  PrintSecurityAssociationStringParameter(association, "espKey");
  PrintSecurityAssociationStringParameter(association, "ahAlgorithm");
  PrintSecurityAssociationStringParameter(association, "ahKey");
  PrintSecurityAssociationNumberParameter(association, "windowSize");
  PrintSecurityAssociationNumberParameter(association, "esn");

  // release the association object when it isn't needed anymore
  ipsecAssociationRelease(association);
}

void PrintSecurityAssociationStringParameter(long handle, char parameterName[])
{
  char value[100];
  if(ipsecAssociationGetParameter(handle, parameterName, value) >= 0)
  {
    write("%s: %s", parameterName, value);
  }
}

void PrintSecurityAssociationAddressParameter(long handle, char parameterName[])
{
  char value[100];
  ip_Endpoint ep;
  if(ipsecAssociationGetParameter(handle, parameterName, ep) == 0)
  {
    ep.PrintEndpointToString(value);
    write("%s: %s", parameterName, value);
  }
}

void PrintSecurityAssociationNumberParameter(long handle, char parameterName[])
{
  dword value;
  if(ipsecAssociationGetParameter(handle, parameterName, value) == 0)
  {
    write("%s: %u", parameterName, value);
  }
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

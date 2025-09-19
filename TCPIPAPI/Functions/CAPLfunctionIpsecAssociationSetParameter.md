[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpsecAssociationSetParameter.md)

**CAPL Functions** » **TCP/IP API** » **ipsecAssociationSetParameter**

# ipsecAssociationSetParameter

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
The function is dependent on the selected stack.  
It is not possible to modify the security association database of the operating system TCP/IP stack.

## Function Syntax

- `long ipsecAssociationSetParameter(long association, char[] parameter, char[] value);  // form 1`
- `long ipsecAssociationSetParameter(long association, char[] parameter, byte[] value);  // form 2`
- `long ipsecAssociationSetParameter(long association, char[] parameter, IP_Endpoint value); // form 3`
- `long ipsecAssociationSetParameter(long association, char[] parameter, dword value);  // form 4`

## Description

Set the value of a parameter in a IPsec security association record. To modify the security association database it is necessary to call [ipsecAssociationDatabaseUpdate](CAPLfunctionIpsecAssociationDatabaseUpdate.md).

A security association record can be created with [ipsecAssociationInit](CAPLfunctionIpsecAssociationInit.md) or with [ipsecAssociationDatabaseGetSpi](CAPLfunctionIpsecAssociationDatabaseGetSpi.md).

## Parameters

- **association**: Handle to an association object.
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
  - **spi**: Returns the security parameter index of the security association
  - **espalgorithm**: Returns the used esp algorithm. Possible values are: NONE, AES, AES128, AES192, AES256
  - **espkey**: Returns the key of the esp algorithm
  - **ahalgorithm**: Returns the used esp algorithm. Possible values are: NULL, SHA2_512, SHA512, AES192GMAC, AES128GMAC, SHA256, SHA2_256, SHA2_384, SHA384, SHA, SHA1, AES256GMAC, AESCMAC, SHA1_160, NONE
  - **ahkey**: Returns the key of the esp algorithm
  - **windowSize**: replay window size in byte
  - **esn**:
    - **0**: extended sequence number disabled
    - **1**: extended sequence number enabled
- **value**: The value to set in the security association record.

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
  dword socket;
  long association;
  dword addressCount;
  ip_Address adapterAddress[1];
  ip_Endpoint localEndpoint;

  // add a policy
  IpSecPolicyDatabaseAdd(ip_Endpoint(0.0.0.0:0), 0, ip_Endpoint(192.168.1.10:0), 24, "any", "out ipsec ah/transport//require");

  // create a security associaton in the database from the current node to the node 192.168.1.10
  ipGetAdapterAddress(1, adapterAddress, addressCount);
  localEndpoint.Address = adapterAddress[0];
  association = ipsecAssociationDatabaseGetSpi(localEndpoint, ip_Endpoint(192.168.1.10), "ah", "any");

  // set the ah algorithm and key
  ipsecAssociationSetParameter(association, "ahalgorithm", "sha");
  ipsecAssociationSetParameter(association, "ahkey", "0123456789ABCDEF");

  // update the security association in the database
  ipsecAssociationDatabaseUpdate(association);

  // release the association object when it isn't needed anymore
  ipsecAssociationRelease(association);

  // send data which maches the policy
  socket = udpOpen(ip_Endpoint(0.0.0.0:0));
  udpSendTo(socket, ip_Endpoint(192.168.1.10:23), "hello world", 11);
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

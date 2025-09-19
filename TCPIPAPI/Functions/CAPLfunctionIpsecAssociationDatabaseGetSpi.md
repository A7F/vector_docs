[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpsecAssociationDatabaseGetSpi.md)

## ipsecAssociationDatabaseGetSpi

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » ipsecAssociationDatabaseGetSpi

**Valid for**: CANoe DE • CANoe4SW DE

### Note

- The function is dependent on the selected stack.
- It is not possible to modify the security association database of the operating system TCP/IP stack.

### Function Syntax

```plaintext
long ipsecAssociationDatabaseGetSpi(IP_Endpoint source, IP_Endpoint destination, char[] protocol, char[] mode);
```

### Description

With this function, it is possible to create a security association in the security association database of the current network stack. The stack will assign a free SPI to the security association. After the creation, it is possible to modify the security association record with [ipsecAssociationSetParameter](CAPLfunctionIpsecAssociationSetParameter.md) and update the security association in the database by calling [ipsecAssociationDatabaseUpdate](CAPLfunctionIpsecAssociationDatabaseUpdate.md).

### Parameters

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

### Return Values

- **>0**: A valid security association record handle.
- **-1**: Failed

### Example

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

  // create a security association in the database from the current node to the node 192.168.1.10
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

  // send data which matches the policy
  socket = udpOpen(ip_Endpoint(0.0.0.0:0));
  udpSendTo(socket, ip_Endpoint(192.168.1.10:23), "hello world", 11);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

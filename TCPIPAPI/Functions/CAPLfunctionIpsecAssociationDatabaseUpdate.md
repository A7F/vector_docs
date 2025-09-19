[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpsecAssociationDatabaseUpdate.md)

**CAPL Functions** » **TCP/IP API** » **ipsecAssociationDatabaseUpdate**

# ipsecAssociationDatabaseUpdate

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
The function is dependent on the selected stack. It is not possible to modify the security association database of the operating system TCP/IP stack.

## Function Syntax

```plaintext
long ipsecAssociationDatabaseUpdate(long association);
```

## Description

With this function it is possible to update an existing security association in the security association database of the current network stack. This is necessary after modifying a security association record with [ipsecAssociationSetParameter](CAPLfunctionIpsecAssociationSetParameter.md).

## Parameters

- **association**: Handle to a security association record object.

## Return Values

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

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

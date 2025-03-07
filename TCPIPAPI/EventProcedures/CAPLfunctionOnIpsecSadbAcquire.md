[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/EventProcedures/CAPLfunctionOnIpsecSadbAcquire.md)

**CAPL Functions** » **TCP/IP API** » **OnIpsecSadbAcquire**

# OnIpsecSadbAcquire

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- The function is dependent on the selected stack.
- This functionality cannot be used in connection with the operating system TCP/IP stack.

## Function Syntax

```plaintext
void OnIpsecSadbAcquire(ip_Endpoint source, ip_Endpoint destination, long policyHandle);
```

## Description

Get a parameter from a security policy record.

## Parameters

- **source**: Source endpoint for which the security association is acquired.
- **destination**: Destination endpoint for which the security association is acquired.
- **policyHandle**: Handle to the security policy which caused the acquire callback.

## Return Values

—

## Example

```plaintext
variables
{
  UdpSocket socket;
}

on start
{
  // add a policy
  IpSecPolicyDatabaseAdd(ip_Endpoint(0.0.0.0:0), 0, ip_Endpoint(192.168.1.0:0), 24, "any", "out ipsec ah/transport//require");

  // open a udp socket
  socket = UdpSocket::Open(ip_Endpoint(0.0.0.0:0));
}

on key 's'
{
  // try to send data which matches the policy -> the first time will trigger OnIpsecSadbAcquire because there is no security association.
  // The first packet will be discarded because the policy requires IPsec.
  socket.SendTo(ip_Endpoint(192.168.1.10:12345), "hello world", 11);
}

// add a security policy in the acquire callback
void OnIpsecSadbAcquire(ip_Endpoint source, ip_Endpoint destination, long policyHandle)
{
  char protocol[20];
  char mode[20];
  long sa;
  char sourceEP[50];
  char remoteEP[50];

  source.PrintEndpointToString(sourceEP);
  destination.PrintEndpointToString(remoteEP);
  write("acquire a security association from source: %s to destination: %s", sourceEP, remoteEP);

  ipsecPolicyGetParameter(policyHandle, "protocol", protocol);
  ipsecPolicyGetParameter(policyHandle, "mode", mode);

  // create a security association in the database
  sa = IPsecAssociationDatabaseGetSpi(source, destination, protocol, mode);

  // set the ah algorithm and key
  ipsecAssociationSetParameter(sa, "ahalgorithm", "sha");
  ipsecAssociationSetParameter(sa, "ahkey", "0123456789ABCDEF");

  // update the security association in the database
  ipsecAssociationDatabaseUpdate(sa);

  // release the association object
  ipsecAssociationRelease(sa);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
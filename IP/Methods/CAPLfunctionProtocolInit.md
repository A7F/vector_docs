[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionProtocolInit.md)

## ethernetPacket::protocol::Init

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::protocol::Init

### Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
long ethernetPacket.<protocol>.Init();
```

### Description

Initialize the protocol within an Ethernet packet. It appends the protocol, if it is not already contained in the packet and initialized the protocol header with default values. If a protocol requires other underlaying protocols, it will add these protocols too, i.e. if the UDP protocol is initialized it also adds an IPv4 protocol header by default. If a specific protocol stack is required, the `Init()` function can be called for every protocol from the lower protocols to the upper protocols, i.e. if UDP over IPv6 is required, first initialize IPv6 and then UDP. Higher protocols than the one which is initialized, will be removed.

### Parameters

—

### Return Values

- **0**: Success
- **-1**: Error

### Example

```plaintext
ethernetPacket packet;
ip_Address 198.128.1.81 addressSrc;
ip_Address 255.255.255.255 addressDst;

packet.ipv4.Init();
packet.SetSourceIPAddress(addressSrc);
packet.SetDestinationIPAddress(addressDst);
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

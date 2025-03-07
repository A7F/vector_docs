[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Objects/CAPLfunctionEthernetPort.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPort::<NetworkName>::<PortName>

# ethernetPort::<NetworkName>::<PortName>

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
ethernetPort ethernetPort.<NetworkName>.<PortName>;
```

## Description

Initializes a variable of type **ethernetPort** with a port qualification.

## Parameters

- **NetworkName**: Name of the Ethernet network.
- **PortName**: Name of the port.

## Selectors

- **name**: Full name as `<networkname>::<portname>` like for [lookupEthernetPort](../Functions/CAPLfunctionLookupEthernetPort.md). Type: Char*, Access: Read only
- **portname**: Name of the port without network name. Type: Char*, Access: Read only
- **networkname**: Name of the network, the port belongs to. Type: Char*, Access: Read only
- **segmentname**: Name of the segment, the port belongs to. Note: The segmentname is empty in general for measurement ports, and for simulation ports if the assignment is **automatic mode**. Type: Char*, Access: Read only
- **deviceidentifier**: Name of the device, the port belongs to (Name + HWindex). Note: The **deviceidentifier** can only be accessed in the Simulation Setup. Type: Char*, Access: Read Only, [Network-based access](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) only
- **portid**: Unique internal ID of the port or **-1** if the port is invalid. Type: Int64, Access: Read only
- **porttype**: Flags defining the type of the port as follows:
  - 0x01: port is valid
  - 0x02: port is active
  - 0x04: port is measurement port
  - 0x08: port is simulation port
  - 0x10: port is an active simulation port
  Type: word, Access: Read only

**Note**: The selectors represent the CANoe DE product viewpoint of **ethernetPorts** (simulated- and measurement-ports), not the hardware viewpoint (physical ports and virtual ports). To retrieve hardware viewpoint information, use the CAPL function [ethGetEthernetPortInfos](../Functions/CAPLfunctionEthGetEthernetPortInfos.md).

## Example

```plaintext
on start
{
  ethernetport clientPort;
  clientPort=ethernetport::Ethernet1::ChatClient1;
  // ... do something with clientPort
}
```

**See Also**: [ethSetLinkStatus](../Functions/CAPLfunctionEthSetLinkStatus.md) • [ethGetLinkStatus](../Functions/CAPLfunctionEthGetLinkStatus.md) • [on ethernetStatus](../EventProcedures/CAPLfunctionOnEthernetStatus.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
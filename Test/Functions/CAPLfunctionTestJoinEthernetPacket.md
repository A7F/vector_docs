[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinEthernetPacket.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinEthernetPacket

# TestJoinEthernetPacket

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinEthernetPacket(qword sMAC, qword dMAC, word vlanID, word etherType, dword flags); // form 1`
- `long TestJoinEthernetPacket(dword sIPv4, dword dIPv4, dword protocol, dword sPort, dword dPort, dword flags); // form 2`
- `long TestJoinEthernetPacket(byte sIPv6[], byte dIPv6[], dword protocol, dword sPort, dword dPort, dword flags); // form 3`
- `long TestJoinEthernetPacket(qword sMAC, qword dMAC, word vlanID, word etherType, dword sIPv4, dword dIPv4, dword protocol, dword sPort, dword dPort, dword flags); // form 4`
- `long TestJoinEthernetPacket(qword sMAC, qword dMAC, word vlanID, word etherType, byte sIPv6[], byte dIPv6[], dword protocol, dword sPort, dword dPort, dword flags); // form 5`
- `long TestJoinEthernetPacket(dbNode source, dbNode destination, dword protocol, dword sPort, dword dPort, dword flags); // form 6`
- `long TestJoinEthernetPacket(ip_Endpoint sourceEndpoint, ip_Endpoint destinationEndpoint); // form 7`
- `long TestJoinEthernetPacket(ip_Address sourceAddress, ip_Address destinationAddress); // form 8`
- `long TestJoinEthernetPacket(ethernetPort aEthernetPort, byte direction, qword sMAC, qword, dMAC, word vlanID, word etherType, ip_Endpoint sourceEndpoint, ip_Endpoint destinationEndpoint, dword flags); // form 9`

## Description

Completes the current set of **joined events** with the transmitted event. This function does not wait.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous.

## Parameters

- **sMAC**: The source MAC address of the Ethernet packet that should be awaited (0 means wildcard).
- **dMAC**: The destination MAC address of the Ethernet packet that should be awaited (0 means wildcard).
- **vlanID**: The VLAN ID of the Ethernet packet that should be awaited (0 means wildcard or in case of an Ethernet packet without VLAN tag: not applicable).
- **etherType**: The EtherType of the Ethernet packet that should be awaited (0 means wildcard).
  - **Form 4**: If concrete source and/or destination IPv4 addresses are passed as arguments (no wildcard) the argument etherType is forced to 0x0800 (IPv4).
  - **Form 5**: If concrete source and/or destination IPv6 addresses are passed as arguments (no wildcard) the argument etherType is forced to 0x86DD.
- **flags**: Some flags to configure special behaviors. A value of 0 means all flags are deactivated (default).
  - 0x0001 – only untagged packets without VLAN ID shall be tested
  - 0x0002 – if sMAC is set to 0 the value 0 shall be tested and not wildcard
  - 0x0004 - if dMAC is set to 0 the value 0 shall be tested and not wildcard
  - 0x0008 - if vlanID is set to 0 the value 0 shall be tested and not wildcard
  - 0x0010 - if etherType is set to 0 the value 0 shall be tested and not wildcard
  - 0x0020 - if sIPv4 is set to 0 the value 0 shall be tested and not wildcard
  - 0x0040 - if dIPv4 is set to 0 the value 0 shall be tested and not wildcard
  - 0x0080 - if sIPv6 is set to 0 the value 0 shall be tested and not wildcard
  - 0x0100 - if dIPv6 is set to 0 the value 0 shall be tested and not wildcard
  - 0x0200 - if sPort is set to 0 the value 0 shall be tested and not wildcard
  - 0x0400 - if dPort is set to 0 the value 0 shall be tested and not wildcard
- **sIPv4**: The source IPv4 address of the IPv4 packet that should be awaited (0 means wildcard).
  - **Form 4**: If a concrete IPv4 address is passed as argument (no wildcard) the parameter etherType is automatically forced to 0x0800 (IPv4).
- **dIPv4**: The destination IPv4 address of the IPv4 packet that should be awaited (0 means wildcard).
  - **Form 4**: If a concrete IPv4 address is passed as argument (no wildcard) the parameter etherType is automatically forced to 0x0800 (IPv4).
- **protocol**: The transport protocol, specified in the header of the IPv4 or IPv6 packet, that should be awaited. Only following values are supported:
  - 6 - TCP
  - 17 - UDP
  - 0 – wildcard
- **sPort**: The transport protocol source port of the IPv4 or IPv6 packet that should be awaited. Only values in range from 0 to 65535 are supported. Greater values are forced to 0 – wildcard.
- **dPort**: The transport protocol destination port of the IPv4 or IPv6 packet that should be awaited. Only values in range from 0 to 65535 are supported. Greater values are forced to 0 - wildcard.
- **sIPv6**: The source IPv6 address of the IPv6 packet that should be awaited (0 means wildcard).
- **dIPv6**: The destination IPv6 address of the IPv6 packet that should be awaited (0 means wildcard).
- **source**: Simulation node from which the awaited packet should be sent. Node’s MAC or IPv4 or IPv6 addresses are read from the database. This condition is matched if the tested packet’s source MAC or IPv4 or IPv6 address match one of the node’s ones.
- **destination**: Simulation node to which the awaited packet should be sent. Node’s MAC or IPv4 or IPv6 addresses are read from the database. This condition is matched if the tested packet’s destination MAC or IPv4 or IPv6 addresses match one of the node’s ones.
- **sourceEndpoint**: IP address and UDP/TCP port number of source. If address type is not set, address is used as wildcard. If protocol type is not set, protocol is wildcard.
- **destinationEndpoint**: IP address and UDP/TCP port number of destination. If address type is not set, address is used as wildcard. If protocol type is not set, protocol is wildcard.
- **sourceAddress**: IP address of source. If address type is not set, address is used as wildcard.
- **destinationAddress**: IP address of destination. If address type is not set, address is used as wildcard.
- **ethernetPort**: Ethernet port of the specified PDU.
- **direction**: Direction of the specified PDU. Possible values:
  - 0: Rx only
  - 1: Tx only
  - 2: Rx and Tx

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

—

[TestWaitForEthernetPacket](CAPLfunctionTestWaitForEthernetPacket.md) • [testGetWaitEthernetPacketData](CAPLfunctionTestGetWaitEthernetPacketData.md)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

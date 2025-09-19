[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTOutputMostEthPkt.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » outputMostEthPkt

# outputMostEthPkt

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `outputMostEthPkt(long channel, int64 destMacAdr, long dataLen, byte[] data); // form 1`
- `outputMostEthPkt(long channel, long prio, long retryCount, int64 sourceMacAdr, int64 destMacAdr, long dataLen, byte[] data); // form 2`

## Description

Sends out an Ethernet packet over the asynchronous channel.

## Parameters

- **channel**: Application channel number.
- **destMacAdr**: Destination MAC address (6 Byte).
- **dataLen**: Number of data bytes to be sent (2 <= dataLen <= 1506).
- **Data**: Data bytes of the Ethernet packet.
  - **Note**: At least two bytes have to be sent (Ethernet Type Field). In case more than 1502 Bytes should be sent, the VLAN Tag has to be set in the first two data bytes (0x81, 0x00).
- **prio**: Sending priority of the Ethernet packet.
  - **Note**: Value range: 0x01..0x07. The value "-1" is also valid and used as wildcard to set the default priority (0x07).
- **retryCount**: Number of retries.
  - **Note**: Value range: 0x00..0x07. The value "-1" is also valid and used as wildcard to set the number of retries configured for the asynchronous channel (see [mostSetRetryParameter](CAPLFunctionMOSTSetGetRetryParameter.md)).
- **sourceMacAdr**: Source MAC address. (6 Byte).
  - **Note**: It is possible to set another source MAC address as the own one. The value "-1" is also valid and is used as wildcard to set the own MAC address.

## Example

—

[mostSetMasterMode](CAPLfunctionMOSTSetGetMasterMode.md) • [mostGenerateBusloadEthPkt](CAPLfunctionMOSTGenerateBusloadEthPkt.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

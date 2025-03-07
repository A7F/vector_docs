[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTConfigureBusloadEthPkt.md)

**CAPL Functions** » **MOST** » **mostConfigureBusloadEthPkt**

# mostConfigureBusloadEthPkt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2640.

## Function Syntax

```plaintext
long mostConfigureBusloadEthPkt(long channel, long rate, long countertype, long counterpos, int64 srcadr, int64 destadr, long datalen, BYTE data[]);
```

## Description

The function configures the busload generator for the Ethernet channel. As an option, the packets can be supplied with a sequence counter. Load generation can be started with the [mostGenerateBusloadEthPkt](CAPLfunctionMOSTGenerateBusloadEthPkt.md) function.

**Note**  
Busload can also be generated without CAPL programming using the MOST Stress Window.

## Parameters

- **channel**: Channel of the connected interface.
- **rate**: Number of Ethernet packets per second. The maximum transmission rate depends on the packet length, the synchronous bandwidth control (SBC) and the MOST loop frequency. Due to arbitration delays, the busload actually generated can deviate from the specified rate.
- **countertype**: Sequence counter type:
  - `0`: No sequence counter
  - `1`: 1 byte counter
  - `2`: 2 byte counter (higher quality byte first)
  - `3`: 3 byte counter (higher quality bytes first)
  - `4`: 4 byte counter (higher quality bytes first)
- **counterpos**: Position of the lowest counter byte.
- **srcadr**: Source MAC address. (6 Byte).

  **Note**  
  It is possible to set another source MAC address as the own one. The value "-1" is also valid and is used as wildcard to set the own MAC address.

- **destadr**: Target MAC address (6 Byte).
- **dataLen**: Number of data bytes to be sent (2 <= dataLen <= 1506).
- **data**: Data bytes of the Ethernet packet.

  **Note**  
  At least two bytes have to be sent (Ethernet Type Field). In case more than 1502 Bytes should be sent, the VLAN Tag has to be set in the first two data bytes (0x81, 0x00).

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

See [mostGenerateBusloadEthPkt](CAPLfunctionMOSTGenerateBusloadEthPkt.md).

[mostGenerateBusloadEthPkt](CAPLfunctionMOSTGenerateBusloadEthPkt.md) • [mostSetStressNodeParameter](CAPLfunctionMOSTSetGetStressNodeParameter.md) • [mostSetMacAdr](CAPLfunctionMOSTSetGetMacAdr.md) • [mostSetSBC](CAPLfunctionMOSTSetSBC.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTEthPkt.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostEthPkt

# OnMostEthPkt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
OnMostEthPkt(long pktDataLen);
```

## Description

When an Ethernet packet is received over the Packet Data Channel the `OnMostEthPkt` event procedure is called.

The following functions are available for evaluating the event:

- `long mostEventChannel()`

  Returns the channel of the packet event.

- `long mostEventTime()`

  Returns the time stamp of the event (Units: 10 µs).

- `float mostEventTimeNs()`

  Returns the time stamp of the event (Units: 1 ns).

- `long mostEventOrigTime()`

  Returns the hardware generated time stamp of the event (Units: 10 µs).

- `int64 mostEthPktSrcMacAdr(), int64 mostEthPktDestMacAdr()`

  Returns the 48 bit source or destination Ethernet address.

- `long mostEthPktDir()`

  Returns the direction of transmission (Rx=0, Tx=1, TxRe-quest=2).

- `long mostEthPktDlc()`

  Number of transported data bytes.

- `long mostEthPktGetData(byte[] buffer, long cnt)`

  Tries to copy cnt data bytes to a provided buffer. Returns the actual number of copied bytes.

- `long mostEthPktGetSelData(byte[] buffer, long begin, long cnt)`

  Tries to copy cnt data bytes starting at byte position 'begin' to a provided buffer. Returns the actual number of copied bytes.

- `long mostEthPktIsSpy()`

  Returns 1 if the packet was received over the Spy of the Packet Data Channel, otherwise 0.

- `long mostEthPktAck()`

  Returns the acknowledge code.

- `long mostEthPktPAck()`

  Returns the preemptive acknowledge code (for mostEthPktIsSpy()=1 only).
  (0x00: No Response; 0x01: Buffer full; 0x04: OK)

- `dword mostEthPktCRC()`

  Returns the CRC value (for mostEthPktIsSpy()=1 only).

- `long mostEthPktCAck()`

  Returns the CRC acknowledge code (for mostEthPktIsSpy()=1 only).
  (0x00: No Response; 0x01: CRC error; 0x04: OK)

In nodal sequences (Measurement Setup) a received packet can be passed to the next node by the [outputMostEthPktThis](../Functions/CAPLfunctionMOSTOutputMostEthPktThis.md) command.

## Parameters

- **pktDataLen**: Number of data bytes of the packet.

## Return Values

—

## Example

—

[mostSetMacAdr](../Functions/CAPLfunctionMOSTSetGetMacAdr.md) • [OnMostMacAdr](CAPLfunctionOnMOSTMacAdr.md) • [mostEthPktSetTraceColors](../Functions/CAPLfunctionMOSTEthPktSetTraceColors.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTPkt.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostPkt

# OnMostPkt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

`OnMostPkt(long pktdatalen);`

## Description

When a packet is received over the Asynchronous Channel the `OnMostPkt()` event procedure is called.

The following functions are available for evaluating the event:

- `long mostPktMsgChannel()`
  - Returns the channel of the packet event.
- `long mostPktMsgTime()`
  - Returns the time stamp of the event (Units: 10 µs).
- `float mostPktMsgTimeNs()`
  - Returns the time stamp of the event (Units: 1 ns).
- `long mostPktOrigTime()`
  - Returns the hardware generated time stamp of the event (Units: 10 µs).
- `long mostPktSrcAdr(), long mostPktDestAdr()`
  - Returns the source or destination address
- `long mostPktDir()`
  - Returns the direction of transmission (Rx=0, Tx=1, TxRequest=2)
- `long mostPktArbitration()`
  - Returns the packet arbitration value
- `long mostPktDlc()`
  - Number of transported data bytes (= Source address + Number of used quadlets = 2 + N*4; N = 0,1,2...)
- `long mostPktGetData(byte[] buffer, long cnt)`
  - Tries to copy cnt data bytes to a provided buffer. Returns the actual number of copied bytes.
- `long mostPktGetSelData(byte[] buffer, long begin, long cnt)`
  - Tries to copy cnt data bytes starting at byte position 'begin' to a provided buffer. Returns the actual number of copied bytes.
- `long mostPktTelID()`
  - Returns the TelID of the packet (upper four bits of data byte 4)
- `long mostPktTelLen()`
  - Returns the TelLen of the packet (comprised of data bytes 4 and 5)
- `long mostPktIsSpy()`
  - Returns 1 if the packet was received over the Spy of the asynchronous channel, otherwise 0.
- `long mostPktAck()`
  - Returns the acknowledge code (MOST150 only).
- `long mostPktPAck`
  - Returns the preemptive acknowledge from the potential packet receiver(s) to the packet transmitter (for mostEthPktIsSpy()=1 and MOST150).  
  (0x00: No Response; 0x01: Buffer full; 0x04: OK)
- `long mostPktCRC`
  - Returns the CRC value (for mostPktIsSpy()=1 and MOST150).
- `long mostPktCAck()`
  - Returns the CRC acknowledge code (for mostPktIsSpy()=1 and MOST150).  
  (0x00: No Response; 0x01: CRC error; 0x04: OK)

In nodal sequences (Measurement Setup) a received packet can be passed to the next node by the [outputMostPktThis](../Functions/CAPLfunctionMOSTOutputMostPktThis.md) command.

## Parameters

- **pktdatalen**: Number of data bytes of the packet.

## Return Values

—

## Example

Access to packet data:

```plaintext
OnMostPkt(long pktDataLen)
{
    byte data[1524];
    long i, bytesdisp;
    write("Packet detected on channel %d", mostPktMsgChannel());
    // copy packet data to local buffer
    mostPktGetData(data, pktDataLen);
    // output first data bytes
    bytesdisp = pktDataLen > 10 ? 10 : pktDataLen;
    for(i = 0; i < bytesdisp; i++)
    {
        write("Byte %03d: %02X", i, data[i]);
    }
    // forward packet to the next node
    outputMostPktThis();
}
```

[outputMostPkt](../Functions/CAPLfunctionMOSTOutputMostPkt.md) • [outputMostPktThis](../Functions/CAPLfunctionMOSTOutputMostPktThis.md) • [mostPktSetTraceColors](../Functions/CAPLfunctionMOSTPktSetTraceColors.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

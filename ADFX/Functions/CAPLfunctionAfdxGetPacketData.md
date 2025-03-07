[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxGetPacketData.md)

**CAPL Functions** » **AFDX** » **AfdxGetPacketData**

# AfdxGetPacketData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxGetPacketData( long packet, long offset, long length, byte buffer[] );
```

## Description

This function copies the packet content (including protocol header and payload) to a local buffer.

## Parameters

- **packet**: Handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md) or from within a callback.
- **offset**: This is the offset from the beginning of the Ethernet packet. If this is 0, data is copied starting at byte 0 frame (destination MAC address).
- **length**: This is the number of bytes to be copied from Ethernet packet to the specified buffer.
- **buffer**: Buffer in which the requested data are copied. Make sure that the size of the buffer is at least **length** bytes.

## Return Values

- Number of copied data bytes.
- With [AfdxGetLastError](CAPLfunctionAfdxGetLastError.md) you can check if the function has been processed successfully.

## Example

```plaintext
void OnAfdxRawPacket( long dir, long line, int64 timestamp, long bag, long afdxFlags, long packet )
{
  byte rawdata[8330];
  long packetLength;
  long rxLength;
  long packetHandle;
  long msgId;

  if (afdxFlags & packetIsReassembled) {
    write( "<%NODE_NAME%> OnAfdxRawPacket: packet is JumboPacket --> skip" );
    return; // don't transfer Jumbo-frames
  }
  if (afdxFlags & packetIsFragmented) {
    write( "<%NODE_NAME%> OnAfdxRawPacket: packet is fragmented" );
  }

  rxLength = AfdxGetPacketData( packet, 0 , elCount(rawdata), rawdata );
  write( "<%NODE_NAME%> AfdxGetPacketData has length: %d", rxLength );

  if (rxLength==0) {
    write ("<%NODE_NAME%> Error empty packet-length at timestamp %u", timestamp / 1000);
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
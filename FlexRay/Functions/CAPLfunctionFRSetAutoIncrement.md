[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRSetAutoIncrement.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frSetAutoIncrement

# frSetAutoIncrement

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void frSetAutoIncrement (int channel, int slotId, int channelMask, int cycleStart, int cycleRepetition, dword flags, int increment_size, int increment_offset);
```

## Description

Part of the payload of a frame will be incremented automatically on each transmission. The number of bytes used can be set to 1, 2, or 4. The byte offset can also be set. The only format supported is Intel (Little Endian).

## Parameters

- **channel**: Channel number (or cluster number)
- **slotId**: Slot number of the frame used.
- **channelMask**: FlexRay channel mask  
  Possible values:
  - 1: Channel A
  - 2: Channel B
  - 3: Channel A+B
- **cycleStart, cycleRepetition**: Cycle multiplexing parameter
- **flags**: 1: Payload increment is switched on. All other values are reserved and must not be used.
- **increment_size**: Number of bits used for the increment.  
  Valid values: 8, 16, 32
- **increment_offset**: Byte position after which the payload is incremented.  
  Possible values:
  - **increment_size 8**: 0,1,2,3...
  - **increment_size 16**: 0,2,4,6,...
  - **increment_size 32**: 0,4,8,...

## Return Values

—

## Example

This example sends automatically a frame each second cycle in slot 30 with automatically incrementing a message counter:

```plaintext
variables
{
   // The gMsg2 message for the static segment
   // that is sent on channel A only.
   frFrame ( 30, 0, 2) gMsg2;
   const BYTE gMsg2Flags    = 0;  // state-driven for repeated transmission
   const BYTE gMsg2Channel  = %CHANNEL%; // send on network the CAPL node is assigned to
   const BYTE gMsg2ChanMask = 1;  // send on FlexRay channel A
   const BYTE gMsg2Len      = 32; // 32 byte user data
   const int gMsg2IncSize   = 16; // 16 bit message counter
   const int gMsg2IncOffset = 0;  // Byte 0 is first byte of message counter
}
on preStart
{
   // Optionally prepare buffer for message gMsg2:
   gMsg2.MsgChannel = gMsg2Channel;
   gMsg2.FR_ChannelMask = gMsg2ChanMask;
   gMsg2.FR_Flags = gMsg2Flags;
   frSetPayloadLengthInByte(gMsg2, gMsg2Len);
   frSetSendFrame( gMsg2 );
   // Define the automatic icrementing message counter:
   frSetAutoIncrement(gMsg2.MsgChannel, gMsg2.FR_SlotID, gMsg2.FR_ChannelMask, gMsg2.FR_CycleOffset, gMsg2.FR_CycleRepetition, 1, gMsg2IncSize, gMsg2IncOffset);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
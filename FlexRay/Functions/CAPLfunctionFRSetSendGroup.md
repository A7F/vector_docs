[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRSetSendGroup.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frSetSendGroup

# frSetSendGroup

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
void frSetSendGroup (int slotId, int channelMask, 
 int groupNo, int cycleStart, int cycleRepetition, long flags, int channel);
```

## Description

Grouped frames, which are transmitted in a CAPL handler (e.g., [on frFrame](../EventProcedures/CAPLfunctionOnFRFrame.md), `on timer`, etc.), are not written to the CC send buffer until it has been ensured that frames with a payload that has not yet been modified and frames with a modified payload have not been mixed together during a FlexRay cycle.

In other words, all frames in the group are sent in the current cycle, or all frames are not sent until the next possible cycle.

**Restrictions**  
The number of frames per group is restricted to four per FlexRay channel (A, B).

## Parameters

- **slotId**: Slot number of the frame used
- **channelMask**: FlexRay channel mask  
  Possible values:
  - 1: Channel A
  - 2: Channel B
  - 3: Channel A+B
- **cycleStart, cycleRepetition**: Cycle multiplexing parameter
- **groupNo**: Group number can be selected as required.
- **flags**: Reserved, must be 0
- **channel**: Channel number (or cluster number)

## Return Values

—

## Example

The frames in slots 8 and 40 are registered as a group. The frames are sent in [on frFrame](../EventProcedures/CAPLfunctionOnFRFrame.md) (10, 0, 1).

The frame in slot 40 was able to be sent in the current CC cycle, but not the other frame. Therefore, the Tx buffers of all frames of the group are not written until slot 40 has been expired.

```plaintext
variables
{
   frFrame MsgChannel1.( 8, 0, 1) gSta1Msg;
   frFrame MsgChannel1.(40, 0, 1) gSta2Msg;
   int flags           = 16; // event-driven
   int channelMask     = 1;
   int payloadlength   = 4;

   int groupNo         = 66;
   int Cnt             = 0;
}
on preStart
{
   // register frame 1:
   gSta1Msg.FR_Channelmask = channelMask;
   gSta1Msg.FR_Flags = flags;
   frSetPayloadLengthInByte(gSta1Msg, payloadlength);
   frSetSendFrame( gSta1Msg );
   // add to send group:
   frSetSendGroup( gSta1Msg.FR_SlotID,
                   gSta1Msg.FR_ChannelMask,
                   groupNo,
                   gSta1Msg.FR_CycleOffset,
                   gSta1Msg.FR_CycleRepetition,
                   0 );
   // register frame 2:
   gSta2Msg.FR_Channelmask = channelMask;
   gSta2Msg.FR_Flags = flags;
   frSetPayloadLengthInByte(gSta2Msg, payloadlength);
   frSetSendFrame( gSta2Msg );
   // add to send group:
   frSetSendGroup( gSta2Msg.FR_SlotID,
                   gSta2Msg.FR_ChannelMask,
                   groupNo,
                   gSta2Msg.FR_CycleOffset,
                   gSta2Msg.FR_CycleRepetition,
                   0 );
}
on frFrame (10, 0, 1)
{
   // we assume that we receive at least a message
   // in slot 10 in cycle 0 on channel A:
   if ((this.FR_Cycle == 0) && (this.FR_ChannelMask == 1))
   {
      // Update is done in cycle 0 only:
      gSta1Msg.byte(0) = Cnt;
      gSta2Msg.byte(0) = Cnt;
      frUpdateStatFrame(gSta1Msg);
      frUpdateStatFrame(gSta2Msg);
      Write("Update of Frames in cycle %d with data %d.", this.FR_Cycle, Cnt);
      if (++Cnt > 255) Cnt = 0;
   }
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

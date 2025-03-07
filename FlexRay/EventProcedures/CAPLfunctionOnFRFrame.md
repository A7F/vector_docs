[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/EventProcedures/CAPLfunctionOnFRFrame.md)

**CAPL Functions** » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » on frFrame

# on frFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This event procedure is only used for the reception of valid frames. To receive Null Frames and erroneous frames, please use the [on frNullFrame](CAPLfunctionOnFRNnullFrame.md) or on [frFrameError](CAPLfunctionOnFRFrameError.md) event procedures.

## Function Syntax

- `on frFrame *; // form 1`
  - This procedure is always called when the frame definitions below do not apply.
- `on frFrame <frame name>; // form 2`
  - Uses a symbolic frame name from the database.
- `on frFrame (<slot ID>, <base cycle>, <cycle repetition>); // form 3`
  - This function is only called for a frame in a certain slot.

## Description

This event procedure is called after a valid data frame has been received in the specified slot and cycle. If two valid data frames are received in the according slot (on channel A and on B) then the event procedure is called up twice (once for each frame).

**Example I**  
In this example, the event procedure is only called for frames whose application channel is 2 and its ID is 5.

`on frFrame MsgChannel2.(5,0,1)`

An optional qualifier can be used to assign the handler to a specific network:

**Example II**  
In this example, the event procedure is only called for specific frames from the application channel that is named "network" in the Simulation Setup.

`on frFrame network.<frame name>`

## Parameters

- `*`
  - Specifies the default procedure. This procedure is called up on all received frames for which no explicit event procedure exists.
- `<frame name>`
  - String that corresponds to a frame name of the database.
- `<slot ID>`
  - This number describes a certain slot. Value range: 1...2047.
- `<base cycle>`
  - This number describes the base cycle. This value must be less than the repetition factor and be in the range: 0...63.
- `<cycle repetition>`
  - This number describes the cycle repetition factor. The value has to be between 1 and 64 and has to be a power of 2.

## Selectors

- **Time**
  - The Rx time stamp that has been synchronized with the global time base in the computer. Timer unit: 10 microseconds, data type: dword. Write-protected!
- **Time_ns**
  - The Rx time stamp that has been synchronized with the global time base in the computer. Timer unit: nanoseconds, data type: int64. Write-protected!
- **MsgChannel**
  - The application channel that the FlexRay interface determines, which received the frame. Write-protected!
- **FR_ChannelMask**
  - Identifies the FlexRay channel of the CC. Write-protected!
- **FR_SlotID**
  - The frame was received in this slot. Write-protected!
- **FR_Cycle**
  - The frame was received in this cycle. Write-protected!
- **FR_PayloadLength**
  - Length of the present payload in 16 Bit words (data type: word). Write-protected!
- **byte(index), word(index), dword(index), qword(index), char(index), int(index), long(index), int64(index), <signal name>**
  - Direct access to the payload/data of the frame. Write-protected!
- **FR_Flags**
  - Provides more detailed status information from the frame header, if necessary. Write-protected!
- **FR_HeaderCRC**
  - Retrieves the CRC in the header of the frame received. Write-protected!
- **FR_Segment**
  - Identifies the segment that this frame is assigned to. Write-protected!
- **FR_Status**
  - Additional status information about the reception buffer of the CC. Write-protected!
- **DIR**
  - Transmission direction of the message. Write-protected!
- **SIMULATED**
  - This flag indicates whether the message was simulated. Write-protected!
- **FR_Payload**
  - This selector allows the access of the payload array. Write-protected!

## Example

The following program reacts on received frames and prints them in the Write Window.

```plaintext
variables
{
   const int cWriteTextSize = 512;
   char writeTxt[cWriteTextSize];
}
float getTime (float time)
{
   // convert NS to SEC:
   return time / 1000000000.0;
}
void myprint(char text[])
{
   write("%s", text);
}
on frFrame *
{
   snprintf(writeTxt, cWriteTextSize, "%10.6f: on FRFrame in slot %2d in cycle %2d on channel %2d with mask %d with Type %2d, Flags 0x%02x, Status 0x%02x, Simulated %d.", getTime(messageTimeNS(this)), this.FR_SlotID, this.FR_Cycle, (int)this.MsgChannel, this.FR_ChannelMask, this.Type, this.FR_Flags, this.FR_Status, this.Simulated);
   myprint(writeTxt);
   output(this); // only required in Measurement Setup
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
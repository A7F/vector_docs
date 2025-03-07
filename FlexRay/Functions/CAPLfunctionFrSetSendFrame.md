[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFrSetSendFrame.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frSetSendFrame

# frSetSendFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `void frSetSendFrame( <frame name>, dword flags ); // form 1`
  - Uses a symbolic frame name from the database.
  
- `void frSetSendFrame( int slotId, int channelMask, int len, int cycleStart, int cycleRepetition, dword flags, int channel ); // form 2`
  - If no database is available all necessary parameters can be set separately, too.
  
- `void frSetSendFrame( <frame object> ); // form 3`
  - If a FRFrame object was created with [frFrame](../Objects/CAPLfunctionFRFrame.md), with this function the object can be registered for sending.

## Description

Configures the hardware for sending the specified message. The call must take place in the `On preStart` routine in the Simulation Setup / transmission branch.

## Parameters

- `<frame name>`
  - String that corresponds to a frame name of the database. The necessary parameters `slotId`, `channelMask`, `len`, `cycleStart` and `cycleRepetition` are taken from the corresponding frame definition of the database.

- `slotId`
  - Identifier of the time slot in which the message should be sent.

- `channelMask`
  - Channel of the transmission message. Values:
    - `1`: Channel A
    - `2`: Channel B
    - `3`: Channel A+B

- `len`
  - Number of databytes (maximum 254 bytes).

- `cycleStart`
  - This number designates the base cycle. This value must be smaller than the repetition factor and lie in the range between 0 and 63. This value together with the repetition factor determines the "Cycle Multiplexing" of the frame. The slot ID and the cycle multiplexing (and the cluster allocation of the FlexRay bus) uniquely identify the message in a FIBEX database.

- `cycleRepetition`
  - This number designates the cycle repetition factor. The value must be between 1 and 64 and be a multiple of 2 (e.g. 1, 2, 4, 8, 16, 32 or 64). This value, together with the base cycle, determines the "Cycle Multiplexing" of the frame. The slot ID and the cycle multiplexing (and the cluster allocation of the FlexRay bus) uniquely identify the message in a FIBEX database.

- `flags`
  - Corresponding bits in the flags set or activate special statuses for the frame to be sent:
    - `0x01`: Sets the sync bit in the header. Only a frame in the static segment may have set this bit. **Changes:** This flag is deprecated! Use function [FRSetKeySlot](CAPLfunctionFrSetKeySlot.md) instead.
    - `0x02`: Sets the start-up bit in the header. If this bit is set, then the sync bit must also be set. **Changes:** This flag is deprecated! Use function [FRSetKeySlot](CAPLfunctionFrSetKeySlot.md) instead.
    - `0x10`: Sets the send mode to event-triggered. If not set, the frame will be transmitted in time-triggered mode.
    - `0x20`: Sets the payload preamble bit. With static frames, the initial data bytes then contain the local NM vector; with dynamic frames, the first two bytes then designate the expanded message ID.
    - `0x100`: Inhibit leading cold start. If set, the CC is not allowed to initialize the cluster communication. **Changes:** This flag is deprecated! Use function [FRSetKeySlot](CAPLfunctionFrSetKeySlot.md) instead.

- `channel`
  - Channel number (or cluster number)

## Return Values

—

## Example

For an example see function [frUpdateStatFrame](CAPLfunctionFRUpdateStatFrame.md).

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Objects/CAPLfunctionFRFrame.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frFrame

# frFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `frFrame <frame name> <frame var>; // form 1`
  - Uses a symbolic frame name from the database.
- `frFrame MsgChannel<num>.<frame name> <frame var>; // form 2`
  - Uses a symbolic frame name from the database and specifies the send channel/cluster.
- `frFrame (<slot ID>, <base cycle>, <cycle repetition>) <frame var>; // form 3`
  - Can be used to define the transmission time without database.
- `frFrame MsgChannel<num>. (<slot ID>, <base cycle>, <cycle repetition>) <frame var>; // form 4`
  - Can be used to define the transmission time and channel/cluster without database.

## Description

Can be used to create a FlexRay send object. The object data can be manipulated by selectors associated with this object. Other object characteristics can be read out from selectors.

Objects are then registered using the [frSetSendFrame](../Functions/CAPLfunctionFrSetSendFrame.md) and are sent using the [frUpdateStatFrame](../Functions/CAPLfunctionFRUpdateStatFrame.md) or [frOutputDynFrame](../Functions/CAPLfunctionFROutputDynFrame.md) functions.

## Parameters

- **MsgChannel`<num>`**: Defines the send channel/cluster. `<num>` must be an integer (e.g. 1, 2, 3, etc.) defining the channel number of the corresponding FlexRay interface.
- **`<frame name>`**: Character string corresponding to a frame name from the database. The required parameters (`<slot ID>`, `<base cycle>`, `<cycle repetition>` and `<channel mask>`) are taken from the corresponding frame definition in the database.
- **`<frame var>`**: Character string defining the object's variable name.
- **`<slot ID>`**: This number designates a specific slot. Its value must be between 1 and 2047.
- **`<base cycle>`**: This number designates the base cycle. This value must be smaller than the repetition factor and lies in the range between 0 and 63. This value, together with the repetition factor, determines the "Cycle Multiplexing".
- **`<cycle repetition>`**: This number designates the cycle repetition factor. The value must be between 1 and 64 and be a multiple of 2 (e.g. 1, 2, 4, 8, 16, 32 or 64). This value, together with the base cycle, determines the "Cycle Multiplexing".

## Selectors — General Use

- **MsgChannel**: The application channel that the FlexRay interface determines, which should send the frame.
- **FR_ChannelMask**: Identifies the FlexRay channel of the CC. A value of 1 will send the frame to channel A, 2 will send it to channel B and 3 to channels A and B.
- **FR_SlotID**: The frame has to be transmitted in this slot.
- **FR_CycleOffset**: FlexRay cycle number of the base cycle. This value must be less than `FR_CycleRepetition`.
- **FR_CycleRepetition**: Repetition factor for transmission times in multiples of a FlexRay cycle. This value must come from the value set {1, 2, 4, 8, 16, 32, 64}.
- **FR_PayloadLength**: Length of the payload to be sent in 16 Bit words (data type: word).
- **byte(index), word(index), dword(index), qword(index), char(index), int(index), long(index), int64(index), `<signal name>`**: Direct access to the payload/data of the frame. The number of valid data bytes is specified by the selector `FR_PayloadLength`. The index is always byte-oriented and counted from 0. If the frame object was initialized via a symbolic name from the database, signal names can also be used directly as selectors for the data range. The raw value of the signal is retrieved or set. The physical value can be retrieved or set by `<signal name>.Phys`.
- **FR_Flags**: Corresponding bits in the flags set or activate special states for the frame to be sent.
  - **Bitmask Values**:
    - `0x01`: Sets the sync bit in the header. Only a frame in the static segment may have set this bit.
    - `0x02`: Sets the start-up bit in the header. If this bit is set, then the sync bit must also be set.
    - `0x10`: Sets the send mode to event-triggered. If not set, the frame will be transmitted in time-triggered mode.
    - `0x20`: Sets the payload preamble bit. With static frames, the initial data bytes then contain the local NM vector; with dynamic frames, the first two bytes then designate the expanded message ID.
    - `0x80`: Tx OFF. The frame is no longer sent, the corresponding slots remain empty. The flag can only be used with VN interfaces.
    - `0x200`: Disable use of In-Cycle-Repetition. Flag has only effect on In-Cycle-Repetition frames.
    - `0x400`: Sets the Null Frame indicator in the header. The flag can only be used with VN interfaces.
    - `0x800`: Use PDU buffer. Setting this flags enables the creation on a frame buffer, while transmitting PDUs is still possible.
- **FR_Payload**: This selector allows the access of the payload array (for using as a byte array parameter in functions).
- **GetPDU(n, P)**: Retrieve the PDU with index `n` in this FlexRay frame. The first PDU has index n = 0, the last PDU has index n = PDUCount() - 1. The parameter `P` must be of type `PDU *`. Return values other than 0 indicate an error.
  - **Return Values**:
    - `0`: Data access successful.
    - `-1`: Wrong bus system.
    - `-2`: This frame does not support accessing PDUs.
    - `-3`: The PDU object is invalid.
    - `-4`: PDU is not of RX type.
    - `-5`: Parameter too small (e.g. array has too less bytes).
    - `-6`: Message or PDU is not available (any more).
    - `-7`: PDU index out of bound. Use selector PDUCount() to determine the number of PDUs.
- **IsContainer()**: Returns 1 if at least one AUTOSAR ContainerIPdu is mapped to this FlexRay frame, 0 otherwise. Negative return values indicate an error.
- **PDUCount()**: Returns the number of all PDUs in this FlexRay frame. The return value includes mapped PDU even with unset update bit. Negative return values indicate an error.
- **PDUOffset()**: Returns the byte offset of the start of the PDU with index `n` in the payload of the FlexRay frame. Negative return values indicate an error.

## Selectors — Test Environment

If the Frame object is created (e.g. FrFrame (1,0,1) receiveFrame;) for use with the TFS function [testGetWaitFrFrameData](../../Test/Functions/CAPLfunctionTestGetWaitFrFrameData.md) or [testGetWaitFrNullFrameData](../../Test/Functions/CAPLfunctionTestGetWaitFrNullFrameData.md) or [testGetWaitFrFrameErrorData](../../Test/Functions/CAPLfunctionTestGetWaitFrFrameErrorData.md), then the following selectors can be used to retrieve the received event information:

- **Time**: The Rx time stamp that has been synchronized with the global time base in the computer (hardware synchronization's reference channel or computer system clock). Timer unit: 10 microseconds, data type: dword.
- **Time_ns**: The Rx time stamp that has been synchronized with the global time base in the computer (hardware synchronization's reference channel or computer system clock). Timer unit: nanoseconds, data type: int64.
- **MsgChannel**: The application channel that the FlexRay interface determines, which received the frame.
- **FR_ChannelMask**: Identifies the FlexRay channel of the CC. With 1 the frame was received on channel A, with 2 on channel B.
- **FR_SlotID**: The frame was received in this FlexRay slot.
- **FR_Cycle**: The frame was received in this FlexRay slot.
- **FR_PayloadLength**: Length of the payload that was received in 16 Bit words (data type: word).
- **byte(index), word(index), dword(index), qword(index), char(index), int(index), long(index), int64(index), `<signal name>`**: Direct access to the payload/data of the frame. The number of valid data bytes is specified by the selector `FR_PayloadLength`.
- **FR_Flags**: Corresponding bits in the flags mirror specific bits in the FlexRay header of the received frame.
- **FR_Payload**: This selector allows the access of the payload array (for using as a byte array parameter in functions).

## Example

**Example 1**

For an example see function [frUpdateStatFrame](../Functions/CAPLfunctionFRUpdateStatFrame.md).

**Example 2**

This is an example for forwarding the payload to other functions.

```plaintext
variables
{
  const dword cFrTTFlag = 0x00;
  const dword cFrETFlag = 0x10;
  const dword cFrPPFlag = 0x20;
  const dword cFrStopFlag = 0x80; // only for VN
  const dword cFrNullFlag = 0x400; // only for VN
}

void foo (byte data[], int bytecount)
{
  // evaluate or set the contents of the data array
}

void example ()
{
  frFrame (1,0,1) myFrame  = { FR_Flags = cFrTTFlag | cFrPPFlag, FR_ChannelMask = 1, FR_PayloadLength = 2 };
  foo (myFrame.FR_Payload, myFrame.FR_PayloadLength * 2);
}
```

**Example 3**

This is an example for using the frame object as a function parameter.

```plaintext
variables
{
  const dword cFrTTFlag = 0x00;
  const dword cFrETFlag = 0x10;
  const dword cFrPPFlag = 0x20;
  const dword cFrStopFlag = 0x80; // only for VN
  const dword cFrNullFlag = 0x400; // only for VN

  frFrame (1,0,1) myFrame  = { FR_Flags = cFrTTFlag | cFrPPFlag, FR_ChannelMask = 1, FR_PayloadLength = 2 };
}

void foo (frFrame * frame)
{
  // evaluate or set the contents of the frame object
}

void example ()
{
  foo (myFrame);
}
```

**Example 4**

This is an example for using the Frame object in arrays.

```plaintext
variables
{
  frFrame (1,0,1) frm1;

  // All objects are equal:
  frFrame (2,0,1) frArray1[10];

  // All objects may be different:
  frFrame * frArray2[3] = { (3,0,1), <FrameNameFromDB>, frm1 };
}
```

[Resolution of Ambiguities](../../../Shared/CAPL/General/ResolveAmbiguities.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

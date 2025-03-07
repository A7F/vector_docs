[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/EventProcedures/CAPLfunctionOnFRSlot.md)

**CAPL Functions** » **FlexRay** » **on frSlot**

# on frSlot

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `on frSlot *; // form 1`

  This procedure is always called if the slot definition as described below **not** apply. It is recommended to use the concrete `on frSlot` callback or the [on frFrame](CAPLfunctionOnFRFrame.md) callback because this general callback produces a high system load.

- `on frSlot <slot ID>; // form 2`

  This function is only called for a certain slot.

- `on frSlot signalname; // form 3`

  This function is only called for the slot containing the signal indicated.

- `on frSlot (signalname1 | signalname2 | ...); // form 4`

  This function is called for any slot containing one of the signals indicated.

- `on frSlot (signalname1, signalname2 , ...); // form 5`

  This function is called for the last slot in the cycle among those slots containing one of the signals indicated. All signals in the list must belong to either the static segment of a cycle or to the same message on the dynamic segment of a cycle.

## Description

This event procedure is called up in each cycle after the slot is past. The event procedure is only called for slots in the static segment.

The event procedure is also called up if no frame is received in the specified slot.

Thus it will synchronously be executed to the FlexRay cycle. Therefore it cannot be used in the Measurement Setup or the analysis branch.

If any frame is not received in the slot, then the event procedure is called with the next slot that contains a frame or at the latest when the next cycle begins. For the **VN interfaces** it will be called approx. 500 microseconds after the slot.

If two frames are received in slot `<slot ID>` (on channel A and B), then the event procedure is called up just once (and in fact, with the frame contents of channel A).

The selectors always reference the contents of the Slot. The **FrameType** selector should be evaluated before further processing.

Value range for n: 1 <= `<slot ID>` <= max. static slot ID of the cluster configuration.

An optional channel parameter for event filtering can be assigned to all functions.

**Example**

In the example, the event procedure is only called for frames whose FlexRay channel 2 ID is 35.

```plaintext
on frSlot MsgChannel2.35
```

**Note**

The following syntax is only possible with databases that do not contain PDUs:

- `on frSlot signalname`
- `on frSlot (signalname1 | signalname2 | ...)`
- `on frSlot (signalname1, signalname2 , ...)`

## Parameters

- `*`: Specifies the default procedure. This procedure is called for all slots for which no explicit event procedure exists.
- `<slot ID>`: This number describes a certain slot. The value must be in the following range: 1 to `<maximum static slot ID>`.
- `signalname`: Signal name

## Selectors

- **Time (data type dword)** / **Time_ns (data type int64)**: The Slot N time stamp that has been synchronized with the global time base in the computer (CAN hardware or computer system clock). Timer unit: 10 microseconds. NS timer unit: nanoseconds. **Write-protected!**

- **msgChannel**: Channel in the tool that the FlexRay CC determines. **Write-protected!**

- **FR_ChannelMask**: Identifies the FlexRay channel of the CC. With 1 the frame was received on channel A, with 2 on channel B. If a frame is received on each channel, only the frame from channel A is returned. **Write-protected!**

- **FR_SlotID**: Always contains the n value. **Write-protected!**

- **FR_Cycle**: Current FlexRay cycle number. **Write-protected!**

- **Type**: Identifies the type of frame (=data type: int) and whether a frame has even been received. Possible values:

  - Normal=1: A valid data frame was received.
  - Error=-1: A faulty frame was received.
  - Null=0: An empty (null) data frame was received.
  - Empty=-2: No frame was received.

  **Important:** If no frame is received in the specified slot, the contents of the **ChannelMask**, **PayloadLength**, **msg**, **Flags**, **HeaderCRC**, **Status**, **DIR** and **SIMULATED** selectors are invalid! **Write-protected!**

- **FR_PayloadLength**: Length of the presented payload in 16Bit words (=data type: word). **Write-protected!**

- **msg**: Payload of the message. The number of valid databytes is specified by the **PayloadLength**. **Write-protected!**

- **FR_Flags**: Provides more detailed status information from the frame header, if necessary. Possible values:

  - 0x1: Null Frame
  - 0x2: Payload valid = msg contains valid data
  - 0x4: Frame set the sync bit.
  - 0x8: Frame set the start-up bit.
  - 0x10: Frame set the payload preamble bit.
  - 0x20: Frame set the reserved bit.
  - 0x40: Frame is faulty.
  - 0x80: The data of the redundant frame is inconsistent on both channels.
  - 0x100: The frame is a dummy frame and was not received by the bus.
  - 0x200: —
  - 0x400: —
  - 0x800: —
  - 0x1000: —
  - 0x2000: —
  - 0x4000: The frame was sent/simulated.
  - 0x8000: The frame was received in asynchronous mode.
  - 0x10000: It is a PDU!
  - 0x20000: PDU Rx Update Bit
  - 0x40000: PDU Tx Update Bit
  - 0x80000: If PDUs are received, this bit indicates a normal frame!
  - 0x100000: Frame is part of the dynamic segment.

  **Write-protected!**

- **FR_HeaderCRC**: Delivers the CRC in the header of the frame received. **Write-protected!**

- **FR_Segment**: This selector always returns **Static** since this event procedure is only permissible for static slots. Possible values:

  - Static=0: Frame belongs to the status segment
  - Dynamic=1: Frame belongs to the dynamic segment

  **Write-protected!**

- **FR_Status**: Delivers additional status information about the reception buffer of the CC, if necessary. Possible values:

  - 0x800: TxConflict: Only with Tx frames: Will be set if there already exists a frame in that slot and cycle. This bit will only be set from the **VN** interface.

  All other bits of the status are reserved. **Write-protected!**

- **DIR (byte data type)**: Transmission direction of the message. Possible values:

  - Tx: Message was send by the hardware.
  - Rx: Message was received.
  - TXRequest: Transmit request

  **Write-protected!**

- **SIMULATED**: This flag indicates whether the message was simulated. Values:

  - 0: Not simulated
  - 1: Simulated

  **Write-protected!**

## Example

The following program executes an action always when the static slot 60 is expired.

```plaintext
on frSlot 60
{
   // slot 60 is over ... do action ...
   // Note: The handler is called even if any frame
   // is not received in this slot!
   if (this.Type == 1) // valid Frame was received in this slot
   {
      // Attention: Frame can be from channel A or B.
      // If received on both, then only frame from channel A
      // will be signaled and retrieved here.
   }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
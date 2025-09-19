# on frPDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `on frPDU <PDU name>; // form 1`

  This handler is called on reception of the symbolically defined PDU.

- `on frPDU *; // form 2`

  This procedure is always called when the PDU definition above does not apply. This means that for a certain PDU either this function or the function above is called.

**Note:** The asterisk form is allowed only in the analysis branch in order to forward the received PDU event to the next CAPL program by calling `output(this);`. The PDUs that are handled by this event procedure cannot be distinguished, because there does not exist any unique selector.

## Description

This procedure is called when a PDU with the corresponding name is received.

- `on frPDU <ID>` is not allowed!

An optional channel parameter for event filtering can be assigned to all handlers:

**Example I:** In this example, the event procedure is only called for PDUs whose application channel is 2 and its name is `<PDU name>`.

- `on frPDU MsgChannel2.<PDU name>`

An optional qualifier can be used to assign the handler to a specific network:

**Example II:** In this example, the event procedure is only called for specific PDUs from the application channel that is named "network" in the Simulation Setup.

- `on frPDU network.<PDU name>`

## Selectors

- **Time (data type dword)** / **Time_ns (data type int64)**

  The Rx time stamp that has been synchronized with the global time base in the computer (hardware synchronization's reference channel or computer system clock). Timer unit: 10 microseconds. NS timer unit: nanoseconds. **Write-protected!**

- **UpdateBit**

  The flag contains the current value of the update bit. **Write-protected!**

- **MsgChannel**

  The application channel that the FlexRay interface determines, which received the PDU. **Write-protected!**

- **FR_ChannelMask**

  Identifies the FlexRay channel of the CC. With 1 the PDU's frame was received on channel A, with 2 on channel B. **Write-protected!**

- **FR_SlotID**

  The PDU's frame was received in this slot. **Write-protected!**

- **FR_Cycle**

  The PDU was received in this cycle. **Write-protected!**

- **FR_PayloadLength**

  Length of the present payload in bytes (data type: word). **Write-protected!**

- **byte(index), word(index), dword(index), qword(index), char(index), int(index), long(index), int64(index), `<signal name>`**

  Direct access to the payload/data of the PDU. **Write-protected!**

- **FR_Flags**

  Provides more detailed status information from the frame header, if necessary. Possible values:

  - **0x1** — 
  - **0x2** Payload valid = msg contains valid data
  - **0x4** — 
  - **0x8** — 
  - **0x10** — 
  - **0x20** — 
  - **0x40** — 
  - **0x80** — 
  - **0x100** — 
  - **0x200** — 
  - **0x400** — 
  - **0x800** — 
  - **0x1000** — 
  - **0x2000** — 
  - **0x4000** The PDU was sent/simulated.
  - **0x8000** The PDU was received in asynchronous mode.
  - **0x10000** It is a PDU!
  - **0x20000** PDU Update Bit
  - **0x40000** — 
  - **0x80000** — 
  - **0x100000** PDU is part of the dynamic segment.
  - **0x400000** PDU has an Update Bit.

  All other bits of the flags are reserved. **Write-protected!**

- **FR_HeaderCRC**

  Retrieves the CRC in the header of the frame received. **Write-protected!**

- **FR_Segment**

  Identifies the segment that this frame is assigned to. **Write-protected!**

- **FR_Status**

  Additional status information about the frame's reception buffer of the CC. See [on frFrame](CAPLfunctionOnFRFrame.md). **Write-protected!**

- **DIR**

  Transmission direction of the message. **Write-protected!**

- **SIMULATED**

  This flag indicates whether the message was simulated. **Write-protected!**

- **FR_Payload**

  This selector allows the access of the payload array (for using as a byte array parameter in functions). Available from CANoe DE product 7.2. **Write-protected!**

## Example

The following program reacts on PDUs and prints them in the Write Window.

```plaintext
on frPDU PDU_XY // PDU_XY name from FIBEX database
{
   float var;
   write( "%10.6f: PDU PDU_XY received with update bit = %d!", TimeNowNS()/1000000000.0, this.updateBit);
   var = this.signalname;
   output(this); // only required in Measurement Setup
}
```

[Resolution of Ambiguities](../../../Shared/CAPL/General/ResolveAmbiguities.md)

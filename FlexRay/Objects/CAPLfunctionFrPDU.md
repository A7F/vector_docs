[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Objects/CAPLfunctionFrPDU.md)

**CAPL Functions** » **FlexRay** » **frPDU**

# frPDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `frPDU <FIBEX PDU name> <PDU var>;` // form 1
  - Uses a symbolic PDU name from the database to create a transmission object.
- `frPDU MsgChannel<num>.< FIBEX PDU name> <PDU var>;` // form 2
  - Uses a symbolic PDU name from the database to create a transmission object and specifies the transmission channel/cluster.
- `frPDU <PDU var>;` // form 3
  - Creates a receive object, available only for use with the TFS function [testGetWaitFrPDUData](../../Test/Functions/CAPLfunctionTestGetWaitFrPDUData.md).

## Description

This can be used to create a FlexRay PDU object. The object data can be manipulated via the object's selectors. Additional object properties can be read from the selectors. The object is then registered using the [frSetSendPDU](../Functions/CAPLfunctionFRSetSendPDU.md) and transmitted using the [frUpdatePDU](../Functions/CAPLfunctionFRUpdatePDU.md) functions.

## Parameters

- `<FIBEX PDU name>`
  - String that corresponds to a PDU name in the database.
  - The parameters needed to uniquely identify the PDU are taken from the corresponding PDU definition in the database.
- `<PDU var>`
  - String that specifies the variable name of the object.
- `MsgChannel<num>`
  - Specifies the transmission channel/cluster.
  - `<num>` must be a whole number (e.g., 1, 2, 3, ...) that specifies the channel number of the corresponding FlexRay interface.

## Selectors — General Use

The symbolically defined transmission object contains the following selectors:

- **MsgChannel**: The application channel that the FlexRay interface determines, which should send the PDU.
- **Name**: Returns the symbolic name of the PDU (data type: char array[]). **Write-protected!**
- **FR_ChannelMask**: Identifies the CC's FlexRay channel. With 1, the PDU is transmitted on channel A, with 2 on channel B, and with 3 on channels A and B. **Write-protected!**
- **FR_PDULength**: Length of the PDU's payload to be sent in bytes (data type: word). **Write-protected!**
- **byte(index), word(index), dword(index), qword(index), char(index), int(index), long(index), int64(index), `<signal name>`**: Direct access to the payload/data of the PDU. The number of valid data bytes is specified by the selector **FR_PDULength**. The index is always byte-oriented and counted from 0. Thus, `dword(1)` returns the double word from bytes 1...4 and not from bytes 4...7. Signal names can also be used directly as selectors for the data range. The raw value of the signal is retrieved or set. The physical value can be retrieved or set by `<signal name>.Phys`.
- **FR_Payload**: This selector allows the access of the payload array (for using as a byte array parameter in functions).

## Selectors — Test Environment

If the PDU object is created without the symbolic name (e.g., `FrPDU receivePDU;`) for use with the TFS function [testGetWaitFrPDUData](../../Test/Functions/CAPLfunctionTestGetWaitFrPDUData.md), then it contains the following selectors:

- **Time**: The Rx time stamp that has been synchronized with the global time base in the computer (hardware synchronization's reference channel or computer system clock). The time stamp must be used if time relations should be regarded with events from other sources. **Write-protected!**
- **Time_ns**: The Rx time stamp that has been synchronized with the global time base in the computer (hardware synchronization's reference channel or computer system clock). The time stamp must be used if time relations should be regarded with events from other sources. This time stamp is also output in the Trace Window when receiving a PDU. **Write-protected!**
- **MsgChannel**: The application channel that the FlexRay interface determines, which received the PDU. **Write-protected!**
- **FR_ChannelMask**: Identifies the FlexRay channel of the CC. With 1 the PDU was received on channel A, with 2 on channel B. **Write-protected!**
- **FR_SlotID**: The PDU was received in this FlexRay slot. **Write-protected!**
- **FR_Cycle**: The PDU was received in this FlexRay cycle. **Write-protected!**
- **FR_PayloadLength**: Length of the payload that is received for the PDU in bytes (data type: word). **Write-protected!**
- **byte(index), word(index), dword(index), qword(index), char(index), int(index), long(index), int64(index)**: Direct access to the payload/data of the PDU. The number of valid data bytes is specified by the selector **FR_PayloadLength**. The index is always byte-oriented and counted from 0. Thus, `dword(1)` returns the double word from bytes 1...4 and not from bytes 4...7. **Write-protected!**
- **FR_Payload**: This selector allows the access of the payload array (for using as a byte array parameter in functions). **Write-protected!**

## Example

**Example 1**

For an example see function [frUpdatePDU](../Functions/CAPLfunctionFRUpdatePDU.md).

**Example 2**

This is an example for forwarding the payload to other functions.

```c
void foo (byte[] data, int count)
{
  // evaluate the contents of the data array
}

void example ()
{
  frPDU EngineData myPDU;
  foo (myPDU.FR_Payload, myPDU.FR_PDULength);
}
```

**Example 3**

This is an example for using the PDU object as a function parameter.

```c
variables
{
  frPDU EngineData myPDU;
}

void foo (FrPDU * pdu)
{
  // evaluate or set the contents of the PDU object
}

void example ()
{
  foo (myPDU);
}
```

**Example 4**

This is an example for using the PDU object in arrays.

**Note**: All objects of an array must be initialized with an appropriate PDU definition!

```c
variables
{
  frPDU EngineData pdu1;

  // All objects are equal:
  frPDU EngineData frPDUArray1[10];

  // All objects may be different:
  frPDU * frPDUArray2[2] = { EngineStatus, pdu1 };
}
```

[Resolution of Ambiguities](../../../Shared/CAPL/General/ResolveAmbiguities.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SignalAccess/CAPLfunctionWriteByteArraySignalAsInteger.md)

**CAPL Functions** » [Signal Access](CAPLfunctionsSignalAccessOverview.md) » WriteByteArraySignalAsInteger

# WriteByteArraySignalAsInteger

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword WriteByteArraySignalAsInteger(signal aSignal, qword value, dword byteOrder, dword byteCutMode)` // form 1
- `dword WriteByteArraySignalAsInteger(pdu aPDU, char signalName[], qword value, dword byteOrder, dword byteCutMode)` // form 2

## Description

Writes the value of a byte array signal, treating it as a 64-bit integer. Use this function if you previously wrote the value of a byte array signal with the **.raw64** selector. This selector works only for integer signals, but byte array signals were treated incorrectly as integer signals in *CANoe* versions < 12.0 SP3.

## Parameters

- **aSignal**: A byte array signal
- **aPDU**: An AUTOSAR PDU with a byte array signal
- **signalName**: Name of the signal on the PDU
- **value**: The to be written value.
- **byteOrder**: Byte order for interpreting the signal bytes.
  - 0: little-endian (intel)
  - 1: big-endian (motorola)
  - See examples below.
- **byteCutMode**: How the additional bits of the 64-bit value shall be cut if the signal has less than 64 bits.
  - 0: ignore bits at the end
  - 1: ignore bits at the beginning
  - See examples below.

## Return Values

- **0**: No error
- **1**: The signal has more than 64 bits.
- **-2**: The signal is not a byte array.
- **3**: Signal not found on the PDU (form 2).

## Example

If a signal has 56 bits (7 bytes) and the value shall be written in **motorola** (big-endian) byte order and the given value is 0x9123456789ABCDEF, depending on the **byteCutMode** parameter, the following bytes will be set in the signal:

- `byteCutMode == 0`: 91 23 45 67 89 AB CD
- `byteCutMode == 1`: 23 45 67 89 AB CD EF

If the value shall be written in **intel** (little-endian) byte order, depending on the **byteCutMode** parameter, the following bytes will be set in the signal:

- `byteCutMode == 0`: EF CD AB 89 67 45 23
- `byteCutMode == 1`: CD AB 89 67 45 23 91

[SetRawSignal](../Test/Functions/CAPLfunctionSetRawSignal.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

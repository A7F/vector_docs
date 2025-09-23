# Iso11783TxAbort

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783TxAbort( dword ecuHandle, dword pgn );
```

## Description

Interrupt of a transfer that has previously been started with [Iso11783TxReqPG()](CAPLfunctionIso11783TxReqPG.md). Please note in this regard that for technical reasons, it is only possible to interrupt PGs that are fragmented.

## Parameters

- **ecuHandle**: ECU handle
- **pgn**: Parameter group handle

## Return Values

0 on success or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```
Iso11783TxAbort(ecuHdl, 0xFE09)
```

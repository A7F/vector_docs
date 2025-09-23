# J1939TxAbort

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939TxAbort( dword ecuHandle, dword pgn );
```

## Description

Interrupt of a transfer that has previously been started with [J1939TxReqPG()](CAPLfunctionJ1939TxReqPG.md). Please note in this regard that for technical reasons, it is only possible to interrupt PGs that are fragmented.

## Parameters

- **ecuHandle**: ECU handle
- **pgn**: parameter group handle

## Return Values

0 on success or [error code](../CAPLfunctionsJ1939NLErrorCodes.md)

## Example

```plaintext
J1939TxAbort(ecuHdl, 0xFE09)
```

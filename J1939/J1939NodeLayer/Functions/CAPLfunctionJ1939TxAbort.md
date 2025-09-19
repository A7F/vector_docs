[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939TxAbort.md)

**CAPL Functions** » **J1939** » **J1939 NL** » **J1939TxAbort**

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

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

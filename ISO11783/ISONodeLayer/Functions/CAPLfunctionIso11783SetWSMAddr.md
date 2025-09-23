# Iso11783SetWSMAddr

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783SetWSMAddr( dword ecuHandle, dword wsmAddress );
```

## Description

Use this function to set the address of the Working Set Master, if this ECU is a member of a working set. All parameter groups which are addressed to the Working Set Master are also received by an ECU which calls this function.

## Parameters

- **ecuHandle**: ECU handle
- **wsmAddress**: Address of the Working Set Master for this ECU

## Return Values

0 on success or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```c
Iso11783SetWSMAddr( ecuHdl, 0x06 );
```

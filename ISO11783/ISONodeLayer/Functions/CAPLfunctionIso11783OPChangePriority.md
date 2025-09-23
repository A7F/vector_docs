# Iso11783OPChangePriority

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangePriority( dword ecuHandle, dword maskID, dword priority );
```

## Description

The function changes the priority of an alarm mask. A **Change Priority** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **maskID**: Object ID of an alarm mask
- **priority**: Priority of the alarm mask

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPChangePriority( handle, 1200, 2 );
```

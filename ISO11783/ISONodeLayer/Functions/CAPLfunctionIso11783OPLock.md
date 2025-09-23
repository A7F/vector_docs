# Iso11783OPLock

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPLock( dword ecuHandle, dword lock, dword maskID, dword timeout );
```

## Description

The function locks the screen updates on the Virtual Terminal. A **Lock** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **lock**:
  - 0: unlock
  - 1: lock
- **maskID**: Object ID of the data mask object
- **timeout**: Timeout in [ms]

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPLock( handle, 1200, 1, 500 );
```

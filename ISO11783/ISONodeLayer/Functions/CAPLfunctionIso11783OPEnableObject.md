# Iso11783OPEnableObject

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPEnableObject( dword ecuHandle, dword objectID, dword enable );
```

## Description

The function activates or deactivates an input object. A **Enable Object** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object ID of an input object
- **enable**:
  - 1: activate
  - 0: deactivate

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPEnableObject( handle, 1200, 1 );
```

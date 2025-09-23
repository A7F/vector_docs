# Iso11783OPShowObject

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPShowObject( dword ecuHandle, dword objectID, dword show );
```

## Description

The function shows or hides an object. The **Show Object** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object ID of the object to show or hide
- **show**:
  - 1: show object
  - 0: hide object

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPShowObject( handle, 1200, 1 );
```

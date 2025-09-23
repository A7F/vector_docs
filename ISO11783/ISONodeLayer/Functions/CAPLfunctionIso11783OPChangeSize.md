# Iso11783OPChangeSize

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangeSize( dword ecuHandle, dword objectID, dword width, dword height );
```

## Description

The function changes the size of an object. A **Change Size** command to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object ID of the object
- **width**: Width in pixel
- **height**: Height in pixel

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPChangeSize( handle, 1200, 80, 40 );
```

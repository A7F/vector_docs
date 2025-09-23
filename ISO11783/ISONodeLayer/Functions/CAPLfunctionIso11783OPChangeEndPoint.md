# Iso11783OPChangeEndPoint

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangeEndPoint( dword ecuHandle, dword objectID, dword width, dword height, dword direction );
```

## Description

The function changes the length and alignment of a line object. A **Change End Point** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object ID of the line object
- **width**: Width of the bounding rectangle of the object
- **height**: Height of the bounding rectangle of the object
- **direction**: Alignment of the line
  - 0: from top/left to bottom/right
  - 1: from bottom/left to top/right

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPChangeEndPoint( handle, 1200, 50, 20, 0 );
```

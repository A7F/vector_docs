# Iso11783OPChangeChildPosition

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangeChildPosition( dword ecuHandle, 
 dword parentID, dword objectID, long x, long y );
```

## Description

The function changes the absolute position of an object inside its parent object. A **Change Child Position** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **parentID**: Parent object
- **objectID**: Object which should change its position
- **x**: Absolute X Position inside the parent object
- **y**: Absolute Y Position inside the parent object

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPChangeChildPosition( handle, 1000, 1200, 10, 10 );
```

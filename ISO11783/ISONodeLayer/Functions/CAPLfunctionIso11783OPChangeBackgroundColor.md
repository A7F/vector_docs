# Iso11783OPChangeBackgroundColor

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangeBackgroundColor( dword ecuHandle, 
 dword objectID, dword color );
```

## Description

This function changes the background color of an object. The **Change Background Color** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object ID of the object, which should change the background color
- **color**: Color index

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPChangeBackgroundColor( handle, 1200, 5 );
```

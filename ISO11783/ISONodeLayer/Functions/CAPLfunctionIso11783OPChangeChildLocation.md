# Iso11783OPChangeChildLocation

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangeChildLocation( dword ecuHandle, 
 dword parentID, dword objectID, long dx, long dy );
```

## Description

The function moves an object. The object is moved relative inside the parent object. A **Change Child Location** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **parentID**: Parent object
- **objectID**: Object ID of the object which should be moved
- **dx**: Move X position relative by this value [pixel]
- **dy**: Move Y position relative by this value [pixel]

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
// move object 5 pixels to the right
Iso11783OPChangeChildLocation( handle, 1000, 1200, 5, 0 );
```

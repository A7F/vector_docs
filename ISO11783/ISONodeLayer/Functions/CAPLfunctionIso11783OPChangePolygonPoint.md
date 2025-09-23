# Iso11783OPChangePolygonPoint

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangePolygonPoint( dword ecuHandle, dword polygonID, dword index, dword x, dword y );
```

## Description

The function changes the position of a point of a polygon object. A **Change Polygon Point** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **polygonID**: Object ID of a polygon object
- **index**: Index of the point
- **x**: X position
- **y**: Y position

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPChangePolygonPoint( handle, 1200, 2, 25, 10 );
```

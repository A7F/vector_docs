# Iso11783OPChangePolygonScale

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangePolygonScale( dword ecuHandle, 
 dword polygonID, dword width, dword height );
```

## Description

The function changes the size of a polygon object. A **Change Polygon Scale** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **polygonID**: Object ID of a polygon object
- **width**: Width of the bounding rectangle in pixel
- **height**: Height of the bounding rectangle in pixel

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPChangePolygonScale( handle, 1200, 80, 40 );
```

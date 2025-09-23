[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPChangePolygonScale.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPChangePolygonScale

# Iso11783IL_OPChangePolygonScale

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPChangePolygonScale( dword polygonID, dword width, dword height ); // form 1
long Iso11783IL_OPChangePolygonScale( dbNode implement, dword polygonID, dword width, dword height ); // form 2
```

## Description

The function changes the size of a polygon object. A **Change Polygon Scale** command is sent to the Virtual Terminal.

## Parameters

- **polygonID**: Object ID of a polygon object
- **width**: Width of the bounding rectangle in pixel
- **height**: Height of the bounding rectangle in pixel
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPChangePolygonScale( 1200, 80, 40 );
```

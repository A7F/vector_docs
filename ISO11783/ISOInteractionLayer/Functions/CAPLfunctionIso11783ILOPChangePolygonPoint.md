[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPChangePolygonPoint.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_OPChangePolygonPoint

# Iso11783IL_OPChangePolygonPoint

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPChangePolygonPoint( dword polygonID, dword index, dword x, dword y ); // form 1
long Iso11783IL_OPChangePolygonPoint( dbNode implement, dword polygonID, dword index, dword x, dword y ); // form 2
```

## Description

The function changes the position of a point of a polygon object. A **Change Polygon Point** command is sent to the Virtual Terminal.

## Parameters

- **polygonID**: Object ID of a polygon object
- **index**: Index of the point
- **x**: X position
- **y**: Y position
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPChangePolygonPoint( 1200, 2, 25, 10 );
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

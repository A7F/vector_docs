[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPChangeSize.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPChangeSize

# Iso11783IL_OPChangeSize

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPChangeSize( dword objectID, dword width, dword height ); // form 1
long Iso11783IL_OPChangeSize( dbNode implement, dword objectID, dword width, dword height ); // form 2
```

## Description

The function changes the size of an object. A **Change Size** command to the Virtual Terminal.

## Parameters

- **objectID**: object ID of the object
- **width**: width in pixel
- **height**: height in pixel
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPChangeSize( 1200, 80, 40 );
```

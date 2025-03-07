[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPChangeLineAttr.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPChangeLineAttribute

# Iso11783IL_OPChangeLineAttribute

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPChangeLineAttribute( dword objectID, dword color, dword width, dword art ); // form 1
long Iso11783IL_OPChangeLineAttribute( dbNode implement, dword objectID, dword color, dword width, dword art ); // form 2
```

## Description

The function changes the properties of a line attribute object. A **Change Line** Attribute command is sent to the Virtual Terminal.

## Parameters

- **objectID**: Object ID of a line attribute object
- **color**: Color index
- **width**: Width of line in pixel
- **art**: Bit pattern which is used to draw the line
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPChangeLineAttribute( 1100, 10, 3, 0xaa );
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
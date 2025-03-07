[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPChangeEndPoint.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPChangeEndPoint

# Iso11783IL_OPChangeEndPoint

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPChangeEndPoint( dword objectID, dword width, dword height, dword direction ); // form 1
long Iso11783IL_OPChangeEndPoint( dbNode implement, dword objectID, dword width, dword height, dword direction ); // form 2
```

## Description

The function changes the length and alignment of a line object. A **Change End Point** command is sent to the Virtual Terminal.

## Parameters

- **objectID**: Object ID of the line object
- **width**: Width of the bounding rectangle of the object
- **height**: Height of the bounding rectangle of the object
- **direction**: Alignment of the line
  - 0: from top/left to bottom/right
  - 1: from bottom/left to top/right
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPChangeEndPoint( 1200, 50, 20, 0 );
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
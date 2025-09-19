[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPChangeFillAttr.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_OPChangeFillAttribute

# Iso11783IL_OPChangeFillAttribute

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPChangeFillAttribute( dword objectID, dword color, dword type, dword patternID ); // form 1
long Iso11783IL_OPChangeFillAttribute( dbNode implement, dword objectID, dword color, dword type, dword patternID ); // form 2
```

## Description

The function changes the properties of a fill attribute object. A **Change Fill Attribute** command is sent to the Virtual Terminal.

## Parameters

- **objectID**: Object ID of a fill attribute object
- **color**: Color index
- **type**: Fill type:
  - 0 = do not fill
  - 1 = fill with line color
  - 2 = fill with fill color
  - 3 = fill with pattern from patternID
- **patternID**: Object ID of a picture object, which is used as fill pattern
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPChangeFillAttribute( 1100, 12, 2, 0xFFFF );
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

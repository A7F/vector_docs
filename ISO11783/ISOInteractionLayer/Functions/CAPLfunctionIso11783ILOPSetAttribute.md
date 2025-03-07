[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPSetAttribute.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPSetAttribute

# Iso11783IL_OPSetAttribute

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_OPSetAttribute( dword objectID, dword attributeID, long value ); // form 1`
- `long Iso11783IL_OPSetAttribute( dword objectID, dword attributeID, long value, long options ); // form 2`
- `long Iso11783IL_OPSetAttribute( dbNode implement, dword objectID, dword attributeID, long value, long options ); // form 3`

## Description

The function sets an attribute value of an object. The object must exist in the object pool and support the attribute ID. If the Object Pool API is active, the **Change Attribute** command (175) is sent to the Virtual Terminal. This can be suppressed with Bit 0 in **options**.

## Parameters

- **objectID**: object ID of an object in the object pool
- **attributeID**: attribute ID, see [ISO11783-6](../../../../CANoeCANalyzer/ISO11783/iso11783basics/documentsISO11783.md)
- **value**: new value
- **options**: options
  - Bit 0 and 1 = 0: send **Change Attribute Value** command if parameters are valid
  - Bit 0 and 1 = 1: suppress **Change Attribute Value** command
  - Bit 0 and 1 = 2: force sending **Change Attribute Value** command even if parameters are invalid
  - Bit 0 and 1 = 3: reserved
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **-1108**: value is out of range
- **-1109**: attribute is read only
- **-1110**: object ID not found
- **-1111**: attribute ID not supported

## Example

```plaintext
Iso11783IL_OPSetAttribute( 1000, 3, 20 );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
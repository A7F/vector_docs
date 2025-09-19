[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPGetAttribute.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPGetAttribute

# Iso11783IL_OPGetAttribute

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPGetAttribute( dword objectID, dword attributeID ); // form 1
long Iso11783IL_OPGetAttribute( dbNode implement, dword objectID, dword attributeID ); // form 2
```

## Description

The function returns a value of an object attribute from the local object pool. A **Get Attribute** command is **not** sent to the Virtual Terminal. The object must exist in the object pool and support the attribute ID.

## Parameters

- **objectID**: object identifier of an object in the object pool
- **attributeID**: attribute identifier, see [ISO11783-6](../../../../CANoeCANalyzer/ISO11783/iso11783basics/documentsISO11783.md)
- **implement**: Simulation node to apply the function.

## Return Values

- Integer value of the object.
- If a value of 0 is returned, you can check with the function [Iso11783IL_GetLastError](CAPLfunctionIso11783ILGetLastError.md) if the function succeeded.

## Example

```plaintext
LONG objType;
objType = Iso11783IL_OPGetAttribute( 1000, 0 );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

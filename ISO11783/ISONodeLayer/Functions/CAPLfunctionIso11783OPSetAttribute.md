[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPSetAttribute.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPSetAttribute

# Iso11783OPSetAttribute

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPSetAttribute( dword ecuHandle, dword objectID, dword attributeID, long value );
long Iso11783OPSetAttribute( dword ecuHandle, dword objectID, dword attributeID, long value, long options );
```

## Description

The function sets an attribute value of an object. The object must exist in the object pool and support the attribute ID. If the Object Pool API is active, the **Change Attribute** command (175) is sent to the Virtual Terminal. This can be suppressed with Bit 0 in **options**.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object ID of an object in the object pool
- **attributeID**: Attribute ID, see [ISO11783-6](../../../../CANoeCANalyzer/ISO11783/iso11783basics/documentsISO11783.md)
- **value**: New value
- **options**: Options  
  Bit 0 = 1: suppress **Change Attribute Value** command

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../CAPLfunctionsISONLErrorCodes.md)
- **-1108**: Value is out of range
- **-1109**: Attribute is read only
- **-1110**: Object ID not found
- **-1111**: Attribute ID not supported

## Example

```plaintext
Iso11783OPSetAttribute( handle, 1000, 3, 20 );
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

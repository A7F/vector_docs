[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILOnError.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_OnError**

# FSIL_OnError (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void FSIL_OnError( long errorCode, long param );
```

## Description

Is called if an error has occurred.

## Parameters

- **errorCode**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **param**: Additional parameter depending on the error code

## Return Values

—

## Example

```plaintext
void FSIL_OnError( long errorCode, long param )
{
  write( "Error %d, parameter %d", errorCode, param );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

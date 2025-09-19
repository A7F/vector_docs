[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILOnError.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_OnError**

# GBT27930IL_OnError (Callback)

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
void GBT27930IL_OnError( long errorCode, long param )
```

## Description

This callback function is called from the GBT27930 IL if an error occurred.

## Parameters

- **errorCode**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **param**: additional parameter depending on the error code

## Return Values

—

## Example

```c
void GBT27930IL_OnError( LONG errorCode, LONG param )
{
  write( "Error %d, parameter %d", errorCode, param );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

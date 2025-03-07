[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILGetLastError.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_GetLastError**

# GBT27930IL_GetLastError

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_GetLastError(); // form 1
long GBT27930IL_GetLastError(dbNode node); // form 2
```

## Description

Gets the return value of the last called GBT27930 IL function.

## Parameters

- **node**: Simulation node to apply the function

## Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 't'
{
  BYTE date = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06 };
  GBT27930IL_SetSignalRaw( EEC1::EngSpeed, 6, data );
  write( "Errorcode = %d", GBT27930IL_GetLastError() );
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
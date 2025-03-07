[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILGetLastErrorText.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_GetLastErrorText**

# GBT27930IL_GetLastErrorText

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_GetLastErrorText(dword bufferSize, char buffer[] ); // form 1`
- `long GBT27930IL_GetLastErrorText(dbNode node, dword bufferSize, char buffer[] ); // form 2`

## Description

Returns the result of the last called GBT27930 IL function as string.

## Parameters

- **bufferSize**: size of the return buffer
- **buffer**: return buffer
- **node**: Simulation node to apply the function

## Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 't'
{
    char error[64];
    GBT27930IL_SetCommunicationState( 0xFF );

    GBT27930IL_GetLastErrorText(error );
    write( "Errorcode:  %s", error );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILGetLastErrorText.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_GetLastErrorText

# Iso11783IL_GetLastErrorText

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_GetLastErrorText( dword bufferSize, char buffer[] ); // form 1: deprecated.`
- `long Iso11783IL_GetLastErrorText( char buffer[] ); // form 2`
- `long Iso11783IL_GetLastErrorText( dbNode node, dword bufferSize, char buffer[] ); // form 3: deprecated.`
- `long Iso11783IL_GetLastErrorText( dbNode node, char buffer[] ); // form 4`

## Description

Returns the result of the last called ISO11783 IL function as string.

## Parameters

- **bufferSize**: size of the return buffer
- **buffer**: return buffer
- **node**: Simulation node to apply the function.

## Return Values

- **0**: success
- **< 0**: [error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 't' 
{
  char error[64];
  BYTE date = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06 };
  ISO11783ILSetSignalRaw( EEC1::EngSpeed, 6, data );

  Iso11783IL_GetLastErrorText( error );
  write( "Errorcode: %s", error );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
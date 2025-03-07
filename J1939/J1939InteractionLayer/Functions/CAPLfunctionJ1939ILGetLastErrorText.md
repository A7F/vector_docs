[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILGetLastErrorText.md)

**CAPL Functions** » **J1939** » **J1939 IL** » **J1939ILGetLastErrorText**

# J1939ILGetLastErrorText

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILGetLastErrorText(dword bufferSize, char buffer[] ); // form 1`
- `long J1939ILGetLastErrorText(dbNode node, dword bufferSize, char buffer[] ); // form 2`

## Description

Returns the result of the last called J1939 IL function as string.

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
  BYTE date = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06 };
  J1939ILSetSignalRaw( EEC1::EngSpeed, 6, data );

  J1939ILGetLastErrorText( error );
  write( "Errorcode:  %s", error );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
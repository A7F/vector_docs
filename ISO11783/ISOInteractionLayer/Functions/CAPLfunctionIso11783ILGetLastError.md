[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILGetLastError.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_GetLastError

# Iso11783IL_GetLastError

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_GetLastError(); // form 1
long Iso11783IL_GetLastError(dbNode node); // form 2
```

## Description

Gets the return value of the last called ISO11783 IL function.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: success
- **< 0**: [error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 't'
{
  BYTE date = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06 };
  ISO11783ILSetSignalRaw( EEC1::EngSpeed, 6, data );
  write( "Errorcode = %d", Iso11783IL_GetLastError() );
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

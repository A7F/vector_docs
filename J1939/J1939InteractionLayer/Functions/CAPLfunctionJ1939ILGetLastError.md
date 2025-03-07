[J1939ILGetLastError](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILGetLastError.md)

## J1939ILGetLastError

**CAPL Functions** » **J1939** » **J1939 IL** » J1939ILGetLastError

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

- `long J1939ILGetLastError();` // form 1
- `long J1939ILGetLastError(dbNode node);` // form 2

### Description

Gets the return value of the last called J1939 IL function.

### Parameters

- **node**: Simulation node to apply the function

### Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

### Example

```plaintext
on key 't'
{
  BYTE date = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06 };
  J1939ILSetSignalRaw( EEC1::EngSpeed, 6, data );
  write( "Errorcode = %d", J1939ILGetLastError() );
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OpOnError.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783OPOnError

# Iso11783OPOnError (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783OPOnError( dword ecuHandle, long error, dword vtFunction );
```

## Description

The function is called by the node layer when the object pool detects an error.

## Parameters

- **ecuHandle**: Handle of the ECU
- **error**: Error code, see [error codes](../CAPLfunctionsISONLErrorCodes.md)
  - 1102: Timeout during execution of a VT function, if response is not received
  - 1103: Timeout of the status from VT, Object Pool API changes to state Wait for VT status
- **vtFunction**: VT function which was executed when the error occurred

## Return Values

—

## Example

```c
void Iso11783OPOnError( dword handle, LONG error, dword vtFunction )
{
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939Getlasterror.md)

**CAPL Functions** » **J1939** » **J1939 NL** » J1939GetLastError

# J1939GetLastError

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939GetLastError(void);
```

## Description

This function returns the last error code.

## Parameters

—

## Return Values

[error code](../CAPLfunctionsJ1939NLErrorCodes.md)

## Example

```c
dword errCode;
errCode = J1939GetLastError();
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
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

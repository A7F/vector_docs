[J1939AppErrorIndication](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939AppErrorIndication.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939AppErrorIndication

# J1939AppErrorIndication (Callback)

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939AppErrorIndication( long ecuHandle, long errorClass, long errorNumber, long addCode );
```

## Description

Indicates that errors have occurred during a transfer or else during the initialization of ECUs (for example timeout during the transport protocol). If an Address Claiming procedure has failed, that will also be reported by means of this function.

## Parameters

- **ecuHandle**: ECU handle
- **errorClass**: error class
- **errorNumber**: error number
- **addCode**: additional error parameter, depends on the error number (i.e. the PGN)

## Return Values

—

## Example

```c
dword J1939AppErrorIndication( LONG ecuHdl, LONG errClass, LONG errNum, LONG addCode )
{
  /* user code */
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
[J1587GetParameterByPID](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1587/Functions/CAPLfunctionJ1587GetParameterByPID.md)

[CAPL Functions](../../CAPLfunctions.md) » [J1587](../CAPLfunctionsJ1587Overview.md) » J1587GetParameterByPID

# J1587GetParameterByPID

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
byte J1587GetParameterByPID(J1587Message msg /*in*/, J1587Param param /*out*/, dword dbPID /*in*/)
```

## Description

Gets a J1587 parameter inside a J1708 message given a specific PID.

The function returns an error if a parameter with the specified dbPID is not found inside the J1708 message.

## Parameters

- **msg**: J1708 message
- **param**: returned parameter at the given index
- **dbPID**: database PID

## Return Values

0 or error code

## Example

```plaintext
on J1587Message 50 // 50 is Sender MID, can be dbNode name or MID
{
  dword count, i;
  J1587Param param;

  if (J1587GetParameterByPID(this, param, 80) == 0)
  {
    write ("Parameter with PID 80 received.");
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
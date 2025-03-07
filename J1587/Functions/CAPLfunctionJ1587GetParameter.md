[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1587/Functions/CAPLfunctionJ1587GetParameter.md)

[CAPL Functions](../../CAPLfunctions.md) » [J1587](../CAPLfunctionsJ1587Overview.md) » J1587GetParameter

# J1587GetParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
byte J1587GetParameter(J1587Message msg /*in*/, J1587Param param /*out*/, word index /*in*/)
```

## Description

Gets a J1587 parameter inside a J1708 message at a given index.

## Parameters

- **msg**: J1708 message
- **param**: returned parameter at the given index
- **index**: index of parameter to retrieve

## Return Values

0 or error code

## Example

```plaintext
on J1587Message 50 // 50 is Sender MID, can be dbNode name or MID
{
  dword count, i;
  J1587Param param;
  count = GetParameterCount(this);

  for (i = 0; i < count; i++) 
  {
    if (J1587GetParameter(this, param, i) == 0) 
    {
      write ("Parameter with PID %d received: %d", param.J1587_PID);
    }
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
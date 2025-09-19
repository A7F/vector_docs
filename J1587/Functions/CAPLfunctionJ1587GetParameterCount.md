[J1587GetParameterCount](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1587/Functions/CAPLfunctionJ1587GetParameterCount.md)

[CAPL Functions](../../CAPLfunctions.md) » [J1587](../CAPLfunctionsJ1587Overview.md) » J1587GetParameterCount

# J1587GetParameterCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
word J1587GetParameterCount(J1587Message msg /*in*/)
```

## Description

Gets the count of J1587 parameters inside a given J1708 message that can be used to further calls to [J1587GetParameter()](CAPLfunctionJ1587GetParameter.md).

## Parameters

- **msg**: J1708 message

## Return Values

- number of parameters

## Example

```plaintext
on J1587Message 50 // 50 is Sender MID, can be dbNode name or MID
{
  write ("Number of parameters received: %d", J1587GetParameterCount(this));
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

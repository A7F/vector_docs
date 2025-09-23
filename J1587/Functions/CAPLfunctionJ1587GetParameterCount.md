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

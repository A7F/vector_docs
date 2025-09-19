# CarMaker_Disconnect

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long CarMaker_Disconnect();
```

## Description

Terminates the connection to CarMaker.

## Parameters

—

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```c
on stopMeasurement
{
  gErrorState = CarMaker_Disconnect();
}
```

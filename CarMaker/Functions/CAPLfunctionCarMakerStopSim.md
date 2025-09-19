# CarMaker_StopSim

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long CarMaker_StopSim();
```

## Description

Stops the simulation in CarMaker.

## Parameters

—

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
on stopMeasurement
{
  gErrorState = CarMaker_StopSim();
}
```

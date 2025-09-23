[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionCeil.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » _ceil

# _ceil

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
float _ceil(float x);
```

## Description

Calculates the ceiling of a value, i.e. the smallest integer larger or equal to the value.

## Parameters

- **x**: Value of which the ceiling shall be calculated.

## Return Values

Ceiling of x.

## Example

```plaintext
float x;
x = _ceil(3.6); // x == 4.0
```

[_floor](CAPLfunctionFloor.md) • [_round](CAPLfunctionRound.md)

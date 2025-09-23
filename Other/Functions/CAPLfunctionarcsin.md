# arcsin

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
double arcsin(double x);
```

## Description

Calculates arcsine of x.

## Parameters

- **x**: Value between –1 and 1 whose arcsine is to be calculated. Values outside this range cause a CAPL [runtime error](../CAPLfunctionsRuntimeError.md).

## Return Values

Arcus Sine of x.

## Example

```plaintext
double x;
x = arcsin(1); // result PI/2
x = arcsin(0); // result 0
```

[arccos](CAPLfunctionarccos.md) • [arctan](CAPLfunctionarctan.md)

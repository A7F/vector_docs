# arccos

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
double arccos(double x);
```

## Description

Calculates arccosine of x.

## Parameters

- **x**: Value between –1 and 1 whose arccosine is to be calculated. Values outside this range cause a CAPL [runtime error](../CAPLfunctionsRuntimeError.md).

## Return Values

Arcus Cosine of x.

## Example

```plaintext
double x;
x = arccos(0); // result PI/2
x = arccos(1); // result 0
```

[arcsin](CAPLfunctionarcsin.md) • [arctan](CAPLfunctionarctan.md)

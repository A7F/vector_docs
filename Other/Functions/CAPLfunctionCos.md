[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionCos.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » cos

# cos

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
double cos(double x);
```

## Description

Calculates cosine of x.

## Parameters

Value in radians whose cosine is to be calculated.

## Return Values

Cosine of x.

## Example

```plaintext
double x;
x = cos(PI); // result -1
```

or

```plaintext
double tangens(double x) {
    return sin(x) / cos(x);
}
```

[sin](CAPLfunctionSin.md) • [sqrt](CAPLfunctionSqrt.md) • [exp](CAPLfunctionExp.md)

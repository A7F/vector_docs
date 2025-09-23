[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionPow.md)

**CAPL Functions** » **General** » **Function Overview** » _pow

# _pow

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
double _pow(double x, double y);
```

## Description

Returns x to the power of y.

## Parameters

- **x**: base
- **y**: exponent

## Return Values

x to the power of y.

## Example

```plaintext
double result;
result = _pow(2.0, 3.0); // result == 8.0
result = _pow(4.0, 0.5); // result == 2.0
```

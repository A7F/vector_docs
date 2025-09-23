[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctiongcvt.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » _gcvt

# _gcvt

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
void  _gcvt(double val, int digits, char s[]);
```

## Description

The number **val** is converted to a string **s** containing a decimal point and a possible sign byte.

## Parameters

- **val**: Number to be converted.
- **digits**: Number of significant digits.
- **s**: String, which contains the converted number. If the string size is too small, the string stays unchanged.

## Return Values

—

## Example

```c
char s[15];

float val1 = 3.1415926535;
float val2 = 271828.18284;
_gcvt(val1, 10, s);
writeToLogEx("val1: %f: s: %s", val1, s);
_gcvt(val2, 9, s);
writeToLogEx("val2: %f: s: %s", val2, s);
_gcvt(val2, 5, s);
writeToLogEx("val2: %f: s: %s", val2, s);
_gcvt(val2, 20, s); // String size too small, string stays unchanged
writeToLogEx("val2: %f: s: %s", val2, s);
...
```

Result:

```
val1: 3.141593: s: 3.141592654
val2: 271828.182840: s: 271828.182
val2: 271828.182840: s: 2.7183e+005
val2: 271828.182840: s: 2.7183e+005
```

[atol](CAPLfunctionAtol.md) • [ltoa](CAPLfunctionltoa.md)

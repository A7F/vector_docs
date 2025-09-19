[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionarccos.md)

**CAPL Functions** » **General** » **Function Overview** » **arccos**

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

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionarcsin.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » arcsin

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
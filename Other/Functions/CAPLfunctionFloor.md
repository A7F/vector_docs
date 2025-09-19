[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionFloor.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » _floor

# _floor

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
float _floor(float x);
```

## Description

Calculates the floor of a value, i.e. the largest integer smaller or equal to the value.

## Parameters

- **x**: Value of which the floor shall be calculated.

## Return Values

Floor of x.

## Example

```plaintext
float x;
x = _floor(3.6); // x == 3.0
```

[_ceil](CAPLfunctionCeil.md) • [_round](CAPLfunctionRound.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

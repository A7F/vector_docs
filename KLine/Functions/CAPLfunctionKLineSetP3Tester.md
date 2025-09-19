[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineSetP3Tester.md)

[CAPL Functions](../../CAPLfunctions.md) » [K-Line](../CAPLfunctionsKLineOverview.md) » KLine_SetP3Tester

# KLine_SetP3Tester

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long KLine_SetP3Tester(dword P3_us)
```

## Description

Sets the P3 time which the tester waits until transmitting a further request.

## Parameters

- **P3_us**: P3 time in us.  
  Value range: 0 – 10000000

## Return Values

On success 0, otherwise a value less than 0.

## Example

—

[KLine_SetP4Tester](CAPLfunctionKLineSetP4Tester.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineSetWakeUpTimesTester.md)

[CAPL Functions](../../CAPLfunctions.md) » [K-Line](../CAPLfunctionsKLineOverview.md) » KLine_SetWakeUpTimesTester

# KLine_SetWakeUpTimesTester

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long KLine_SetWakeUpTimesTester(dword TiniL_us, dword Twup_us)
```

## Description

Sets the timings of the fast init wake-up pattern.

## Parameters

- **TiniL_us**: Duration of the low phase in us.  
  Value range: 2000 - 650000

- **Twup_us**: Duration of the wake-up pattern.  
  Value range: 2000 - 650000

## Return Values

On success 0, otherwise a value less than 0.

## Example

—

[KLine_SetInitType](CAPLfunctionKLineSetInitType.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineSetP2max.md)

**CAPL Functions** » **K-Line** » **KLine_SetP2max**

# KLine_SetP2max

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```
long KLine_SetP2max(dword P2max_us)
```

## Description

Sets the maximum time between the client (tester) request and the server (ECU) response, or between 2 server (ECU) responses.

## Parameters

- **P2max_us**: P2max in us  
  Value range: 0 – 100000000 (100 s).

## Return Values

- **0**: Success
- **< 0**: [Error code](../../Diagnostics/CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```c
on start
{
   KLine_SetP2Max(10000000); // P2max == 10 s
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

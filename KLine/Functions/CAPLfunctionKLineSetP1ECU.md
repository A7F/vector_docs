[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineSetP1ECU.md)

**CAPL Functions** » **K-Line** » **KLine_SetP1ECU**

# KLine_SetP1ECU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long KLine_SetP1ECU(dword P1_us)
```

## Description

Sets the interbyte time of a response.

## Parameters

- **P1_us**: P1 in us  
  Value range: 0 – 650000.

## Return Values

On success 0, otherwise a value less than 0.

## Example

```c
on start
{
   KLine_SetP1ECU(10000); // P1 == 10 ms
}
```

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

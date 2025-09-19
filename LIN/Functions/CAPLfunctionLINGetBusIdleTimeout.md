[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetBusIdleTimeout.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linGetBusIdleTimeout

# linGetBusIdleTimeout

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword linGetBusIdleTimeout();
```

## Description

This function returns the currently set bus idle timeout. Depending on the protocol version, the timeout will be specified in bit times (LIN 1.x and Cooling) or in milliseconds (all others).

## Parameters

—

## Return Values

On success, returns the bus idle timeout, otherwise zero.

## Example

—

[linSetBusIdleTimeout](CAPLfunctionLINSetBusIdleTimeout.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

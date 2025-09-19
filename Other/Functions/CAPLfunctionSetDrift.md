[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetDrift.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » setDrift

# setDrift

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void setDrift(int drift);
```

## Description

A constant deviation can be set for the timers of a network node with this function. Inputs for the two values may lie between –10000 and 10000 (corresponds to –100.00% to 100.00%). If the value does not lie within this range, a message is output in the Write Window.

**Note**: Setting of a Drift causes any existing Jitter to be reset.

## Parameters

- **drift**: Integer for the constant deviation.

## Return Values

—

## Example

```plaintext
...
// Sets the Drift to 35.5 percent
setDrift(3550);
...
```

[setJitter](CAPLfunctionSetJitter.md) • [getDrift](CAPLfunctionGetDrift.md) • [getJitterMin](CAPLfunctionGetJitterMin.md) • [getJitterMax](CAPLfunctionGetJitterMax.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

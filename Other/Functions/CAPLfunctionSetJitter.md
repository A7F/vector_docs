[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetJitter.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » setJitter

# setJitter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
setJitter(int min, int max);
```

## Description

The Jitter interval for the timers of a network node can be set with this function. The two values may lie between –10000 and 10000 (corresponds to –100.00% to 100.00%). If one of the two values does not lie within this range, a message is output in the Write Window.

**Note**: Setting of a Jitter will cause any existing Drift to be reset. To utilize Jitter and Drift simultaneously please refer to the example.

## Parameters

- **min**: Integer for the lower interval limit.
- **max**: Integer for the upper interval limit.

## Return Values

—

## Example

```plaintext
...
// Set a Jitter with +–4 percent
setJitter(-400, 400);
...

...
// Set a Jitter with +–4 percent
// and a Drift of 17 percent
setJitter(1300, 2100);
...
```

[getJitterMax](CAPLfunctionGetJitterMax.md) • [getJitterMin](CAPLfunctionGetJitterMin.md) • [setDrift](CAPLfunctionSetDrift.md) • [getDrift](CAPLfunctionGetDrift.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

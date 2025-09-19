[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetJitterMax.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getJitterMax

# getJitterMax

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
int getJitterMax();
```

## Description

Determines the upper limit for the allowable deviation when Jitter is set.

## Parameters

—

## Return Values

Upper deviation in parts per thousand.

## Example

```plaintext
int val;
...
// Assign to val the upper value of the Jitter
val = getJitterMax();
...
```

[getDrift](CAPLfunctionGetDrift.md) • [getJitterMin](CAPLfunctionGetJitterMin.md) • [setDrift](CAPLfunctionSetDrift.md) • [setJitter](CAPLfunctionSetJitter.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

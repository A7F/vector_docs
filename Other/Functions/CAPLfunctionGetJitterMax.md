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

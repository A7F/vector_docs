[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetJitterMin.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getJitterMin

# getJitterMin

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
int getJitterMin();
```

## Description

Determines the lower limit for the allowable deviation when Jitter is set.

## Parameters

—

## Return Values

Lower deviation in parts per thousand.

## Example

```plaintext
int val;
...
// Assign to val the lower value of the Jitter
val = getJitterMin();
...
```

[getDrift](CAPLfunctionGetDrift.md) • [getJitterMax](CAPLfunctionGetJitterMax.md) • [setDrift](CAPLfunctionSetDrift.md) • [setJitter](CAPLfunctionSetJitter.md)

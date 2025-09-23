[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetOEMSleepInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetOEMSleepInd

# linSetOEMSleepInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function can be used for OEM specific variant of LIN protocol only.

## Function Syntax

```
long linSetOEMSleepInd(long active);
```

## Description

Sets/resets the sleep indication bit for a calling slave node.

## Parameters

- **active**
  - 0: set
  - 1: reset

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linCheckOEMSleepInd](CAPLfunctionLINCheckOEMSleepInd.md) • [linGetOEMSleepInd](CAPLfunctionLINGetOEMSleepInd.md)

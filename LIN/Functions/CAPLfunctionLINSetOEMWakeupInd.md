[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetOEMWakeupInd.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linSetOEMWakeupInd

# linSetOEMWakeupInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

This function can be used for OEM specific variant of LIN protocol only.

## Function Syntax

```plaintext
long linSetOEMWakeupInd(long active);
```

## Description

Sets/resets the wake-up indication bit for a calling slave node.

## Parameters

- **active**
  - 0: set
  - 1: reset

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linCheckOEMWakeupInd](CAPLfunctionLINCheckOEMWakeupInd.md) • [linGetOEMWakeupInd](CAPLfunctionLINGetOEMWakeupInd.md)

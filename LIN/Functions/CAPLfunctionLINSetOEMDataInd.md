[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetOEMDataInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetOEMDataInd

# linSetOEMDataInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
This function can be used for OEM specific variant of LIN protocol only.

## Function Syntax

`long linSetOEMDataInd(long active);`

## Description

Sets/resets the data indication bit for a calling slave node.

## Parameters

- **active**
  - 0: set
  - 1: reset

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linCheckOEMDataInd](CAPLfunctionLINCheckOEMDataInd.md) • [linGetOEMDataInd](CAPLfunctionLINGetOEMDataInd.md) • [linSetOEMDataIndTime](CAPLfunctionLINSetOEMDataIndTime.md)

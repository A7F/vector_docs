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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

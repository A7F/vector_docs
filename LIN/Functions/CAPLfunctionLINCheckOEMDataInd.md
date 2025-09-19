[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINCheckOEMDataInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linCheckOEMDataInd

# linCheckOEMDataInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

This function can be used for OEM specific variant of LIN protocol only.

## Function Syntax

```
long linCheckOEMDataInd();
```

## Description

This function checks the data indication bits of all slave nodes defined in the LIN network (the channel is determined by the CAPL program context).

## Parameters

—

## Return Values

- **-1**: Function call not allowed or execution failed.
- **0**: At least one slave has a negative indication.
- **>0**: All slaves reported positive indication.

## Example

—

[linGetOEMDataInd](CAPLfunctionLINGetOEMDataInd.md) • [linSetOEMDataInd](CAPLfunctionLINSetOEMDataInd.md) • [linSetOEMDataIndTime](CAPLfunctionLINSetOEMDataIndTime.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

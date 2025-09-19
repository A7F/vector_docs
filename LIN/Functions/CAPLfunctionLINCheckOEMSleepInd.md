[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINCheckOEMSleepInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linCheckOEMSleepInd

# linCheckOEMSleepInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function can be used for OEM specific variant of LIN protocol only.

## Function Syntax

```plaintext
long linCheckOEMSleepInd()
```

## Description

This function checks the sleep indication bits of all slave nodes defined in the LIN network (the channel is determined by the CAPL program context).

## Parameters

—

## Return Values

- **-1**: Function call not allowed or execution failed.
- **0**: At least one slave has a negative indication.
- **>0**: All slaves reported positive indication.

## Example

—

[linGetOEMSleepInd](CAPLfunctionLINGetOEMSleepInd.md) • [linSetOEMSleepInd](CAPLfunctionLINSetOEMSleepInd.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStartValuesUpdateSymbols.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » startValuesUpdateSymbols

# startValuesUpdateSymbols

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void startValuesUpdateSymbols(char groupName[]);
```

## Description

Sets the variables/signals contained in a specific group to their individual start values in the CANoe DE product [Start Value Window](../../../CANoeCANalyzer/Windows/StartValues/StartValuesWindow.md).

## Parameters

- **groupName**: Name of a group containing variables/signals that are set to their individual start values.
  - If **groupName** is equal to "", then all variables/signals contained in the Start Values Window are set to their individual start values.

## Return Values

—

## Example

```plaintext
on key '3'
{
    startValuesUpdateSymbols("Start values group2");
}

on key '4'
{
    startValuesUpdateSymbols("");
}
```

[startValuesUpdateList](CAPLfunctionStartValuesUpdateList.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

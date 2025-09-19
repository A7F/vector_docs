[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetWriteDbgLevel.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » setWriteDbgLevel

# setWriteDbgLevel

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void setWriteDbgLevel (unsigned int priority);
```

## Description

This function sets the priority level for the [writeDbgLevel](CAPLfunctionWriteDbgLevel.md) CAPL function. The output priority must be set for every network node.

## Parameters

- **priority**: Priority of current CAPL node for output to the Write Window. Ranges for priority: 0 to 15
  - **0**: Only write output with a priority of 0 are shown in the Write Window.
  - **5**: Write output with a priority ranging from 0 to 5 are shown.
  - **15**: All outputs are shown.

## Return Values

—

## Example

```plaintext
int i = 10;
int j = 12;
setWriteDbgLevel(7);
writeDbgLevel (4, "This is shown: h= %lxh",j);
// Output: This is shown: h= 0ch
writeDbgLevel (9, "This is not shown: d= %ld",i);
// No output
```

[write](CAPLfunctionWrite.md) • [writeDbgLevel](CAPLfunctionWriteDbgLevel.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

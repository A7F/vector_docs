[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionWriteDbgLevel.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » writeDbgLevel

# writeDbgLevel

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long writeDbgLevel(unsigned int priority, char format1[], char format2[], ...);
```

## Description

Outputs a message to the Write Window with the specified priority. This function can be used for debugging to vary the output to the Write Window. This function is especially useful if nodelayer-DLL’s are used. In this case the debug output can be controlled using a global priority parameter.

In the simulation tree the priority level can be set for every network node using the [setWriteDbgLevel](CAPLfunctionSetWriteDbgLevel.md) function.

## Parameters

- **priority**: Output priority from 0 to 15.
- **format**: Format string, variables or [expressions](../CAPLFunctionsWriteFormatExpressions.md)

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

[setWriteDbgLevel](CAPLfunctionSetWriteDbgLevel.md) • [write](CAPLfunctionWrite.md) • writeDbgLevel

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

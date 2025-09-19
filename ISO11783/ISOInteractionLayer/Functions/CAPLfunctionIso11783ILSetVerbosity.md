[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILSetVerbosity.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_SetVerbosity

# Iso11783IL_SetVerbosity

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword Iso11783IL_SetVerbosity(dword verbosityLevel); // form 1
dword Iso11783IL_SetVerbosity(dbNode node, dword verbosityLevel); // from 2
```

## Description

Sets verbosity for writing in Write Window.

## Parameters

- **verbosityLevel**
  - 0: do not write messages to the Write Window
  - 1: write only error messages
  - 2: write warning and error messages (default)
  - 3: write information, warning and error messages

- **node**
  - Simulation node to apply the function.

## Return Values

- **0**
  - successful

- **< 0**
  - function call failed

## Example

—

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

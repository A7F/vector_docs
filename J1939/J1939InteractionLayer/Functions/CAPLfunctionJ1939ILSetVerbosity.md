[J1939ILSetVerbosity](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILSetVerbosity.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILSetVerbosity

# J1939ILSetVerbosity

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword J1939ILSetVerbosity(dword verbosityLevel); // form 1
dword J1939ILSetVerbosity(dbNode fs, dword verbosityLevel); // form 2
```

## Description

Sets verbosity for writing in Write Window.

## Parameters

- **verbosityLevel**
  - 0: do not write messages to the Write Window
  - 1: write only error messages
  - 2: write warning and error messages (default)
  - 3: write information, warning and error messages

## Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

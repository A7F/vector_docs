[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILSetVerbosity.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_SetVerbosity**

# TCIL_SetVerbosity

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword TCIL_SetVerbosity( dword verbosityLevel); // form 1
dword TCIL_SetVerbosity( dbNode tc,  dword verbosityLevel); // form 2
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

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)

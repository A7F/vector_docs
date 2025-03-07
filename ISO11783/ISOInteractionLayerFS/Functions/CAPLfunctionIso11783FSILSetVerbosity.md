[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILSetVerbosity.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_SetVerbosity**

# FSIL_SetVerbosity

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `dword FSIL_SetVerbosity(dword verbosityLevel); // form 1`
- `dword FSIL_SetVerbosity(dbNode fs, dword verbosityLevel); // form 2`

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
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

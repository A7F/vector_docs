# ARILResetPDUAsrTXMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILResetPDUAsrTXMode (dbMsg dbMessage);
```

## Description

Resets the current valid transmission mode to the condition that is defined by or-ing all data filters of all signals.

## Parameters

- **dbMessage**: The symbolic name of a PDU in the database.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

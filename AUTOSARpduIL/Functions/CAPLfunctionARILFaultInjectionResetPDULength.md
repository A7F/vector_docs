# ARILFaultInjectionResetPDULength

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILFaultInjectionResetPDULength (dbMsg dbMessage);
```

## Description

Resets the payload length back to its original value from the database.

## Parameters

- **dbMessage**: The symbolic name of a PDU in the database.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

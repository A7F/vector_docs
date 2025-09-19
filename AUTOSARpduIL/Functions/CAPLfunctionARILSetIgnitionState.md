# ARILSetIgnitionState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Note

Setting the ignition state with this function will also update the appropriate global system variable (`sysvar::_ILControl::Ignition`). Therefore the state in all ILs will automatically be set accordingly.

## Function Syntax

```plaintext
long ARILSetIgnitionState (long value);
```

## Description

Activates or deactivates the ignition status globally.

## Parameters

- **value**
  - 0: Set ignition state **off**.
  - 1: Set ignition state **on**.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

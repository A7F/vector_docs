# ARILSetPDUAsrTXMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILSetPDUAsrTXMode (dbMsg dbMessage, long mode, long disturbanceCount, long flags);
```

## Description

Overrides the current valid transmission mode of the PDU. The transmission mode can be **False** or **True**. The current transmission mode is defined by or-ing the current data filter condition value of all signal values of the PDU.

## Parameters

- **dbMessage**: The symbolic name of a PDU in the database.
- **mode**: Sets the **True** timing (**1**) or the **False** timing (**0**) to be active (regardless of the signal values).
- **disturbanceCount**: Reserved/unused; should be set to **-1** (**infinite**)
- **flags**: Reserved; should be set to **0**.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

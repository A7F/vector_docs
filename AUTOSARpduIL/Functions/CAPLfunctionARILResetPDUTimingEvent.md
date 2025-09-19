# ARILResetPDUTimingEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILResetPDUTimingEvent (dbMsg dbMessage, long TrueOrFalse);
```

## Description

Resets the **event-timing** to the values from the database. Possibly two timings (**False** and **True**) exist in parallel and are selected upon the current transmission mode of the PDU.

## Parameters

- **dbMessage**: The symbolic name of a PDU in the database.
- **TrueOrFalse**:
  - 0: denotes the **False** timing
  - 1: denotes the **True** timing
  - 3: denotes the **True** and the **False** timing

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

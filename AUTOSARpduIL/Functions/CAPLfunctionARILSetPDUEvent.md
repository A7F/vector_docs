# ARILSetPDUEvent

**Valid for**: CANoe DE • CANoe4SW DE

## Note

- It is possible to ignore the transmit-model in the database and to generate the transmission event manually.
- It is strongly recommended to use this functionality only for test purposes and not in real simulations. The database should be corrected instead.

## Function Syntax

```plaintext
long ARILSetPDUEvent (dbMsg dbMessage);
```

## Description

A call of this function will lead to a transmission of the associated PDU. This function considers **GenMsgDelayTime**.

## Parameters

- **dbMessage**: The symbolic name of a PDU in the database.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

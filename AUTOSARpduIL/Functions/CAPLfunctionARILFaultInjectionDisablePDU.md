# ARILFaultInjectionDisablePDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILFaultInjectionDisablePDU (dbMsg);
```

## Description

Disables the sending of the PDU except by calling the function [ARILSetPDUEvent](CAPLfunctionARILSetPDUEvent.md).

## Parameters

- **dbMsg**: The symbolic name of a PDU in the database.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

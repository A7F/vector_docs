# ARILControlPDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILControlPDU (dbMsg, dword Control, dword Flags, dword Param1, dword Param2)
```

## Description

Sets/activates/deactivates a special feature/action for a dedicated PDU.

## Parameters

- **dbMsg**: The symbolic name of a PDU in the database.
- **Control**: Determines the action/setting to be applied.
- **Flags**: Flags that can be applied to the action/setting.
- **Param1/Param2**: Parameters that are required for the action/setting.

### Control, Flags, Param1, Param2, Meaning

- **1, Reserved (0), Reserved (0), Reserved (0)**: Enable PDU: corresponds to call of [ARILFaultInjectionEnablePDU](CAPLfunctionARILFaultInjectionEnablePDU.md)
- **2, Reserved (0), Reserved (0), Reserved (0)**: Disable PDU: corresponds to call of [ARILFaultInjectionDisablePDU](CAPLfunctionARILFaultInjectionDisablePDU.md)
- **other, —, —, —**: Reserved – should not be used

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

# ARILControlResume

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Note
- This function can only be used in the CAPL file that is attached to the appropriate node. The corresponding function [ILNodeControlResume](../../CANoeIL/Functions/CAPLfunctionILNodeControlResume.md) can be used in a global node outside or in test modules.
- This function should not be used in the **on PreStart** event procedure.

## Function Syntax

```plaintext
long ARILControlResume (dword flags)
```

## Description

Resumes a suspended IL and starts sending PDUs again.

## Parameters

- **flags**: The value defines the desired resume behavior.
  - 0: IL will leave state **waiting** and enters state **running** (see: [Interaction Layer State Model](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILStateModel.md)).
  - 1: IL will leave state **suspended** and enters state **running** (see: [Interaction Layer State Model](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILStateModel.md)). This is the same effect as calling function [ARILControlStart](CAPLfunctionARILControlStart.md).

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

[ARILControlInit](CAPLfunctionARILControlInit.md) • [ARILControlStart](CAPLfunctionARILControlStart.md) • [ARILControlStop](CAPLfunctionARILControlStop.md) • [ARILControlWait](CAPLfunctionARILControlWait.md)

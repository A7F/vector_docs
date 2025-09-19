# ARILControlWait

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function should not be used in the **on PreStart** event procedure.

## Function Syntax

```plaintext
long ARILControlWait (dword flags)
```

## Description

Stops sending, but accepts signal changes.

## Parameters

- **flags**  
  The value defines the desired wait behavior:
  - 0: IL will enter state **waiting** (see [Interaction Layer State Model](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILStateModel.md)). The IL can be activated by calling [ARILControlResume](CAPLfunctionARILControlResume.md).
  - 1: IL will enter state **suspended** (see [Interaction Layer State Model](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILStateModel.md)). This is the same effect as calling function [ARILControlStop](CAPLfunctionARILControlStop.md). The IL can be activated by calling [ARILControlStart](CAPLfunctionARILControlStart.md).

## Return Values

- **0**  
  No error.
- **Others**  
  [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

[ARILControlInit](CAPLfunctionARILControlInit.md) • [ARILControlResume](CAPLfunctionARILControlResume.md) • [ARILControlStart](CAPLfunctionARILControlStart.md) • [ARILControlStop](CAPLfunctionARILControlStop.md)

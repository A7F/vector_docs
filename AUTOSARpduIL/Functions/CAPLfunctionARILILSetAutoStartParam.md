# ARILSetAutoStartParam

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ARILSetAutoStartParam(dword state)
```

## Description

This function influences the start behavior. The function must be called in [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md), otherwise it will not have any effect.

## Parameters

- **state**: The value defines the desired start behavior:
  - 0: IL will start in state **waiting** (see [Interaction Layer State Model](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILStateModel.md)). The IL can be activated by calling [ARILControlResume](CAPLfunctionARILControlResume.md).
  - 1: IL will start in state **suspended** (see [Interaction Layer State Model](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILStateModel.md)). The IL can be activated by calling [ARILControlStart](CAPLfunctionARILControlStart.md). This is the same effect as calling function [ARILControlInit](CAPLfunctionARILControlInit.md) in [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).
  - 2: IL will start in state **running** (see [Interaction Layer State Model](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILStateModel.md)). PDUs will be sent. This is the default, when the function is not called.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

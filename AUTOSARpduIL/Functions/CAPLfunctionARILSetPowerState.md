# ARILSetPowerState

**Valid for**: [CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

**Note**  
Setting the ignition state with this function will also update the appropriate global system variable (`sysvar::_ILControl::Power`). Therefore the state in all ILs will automatically be set accordingly.

## Function Syntax

```plaintext
long ARILSetPowerState (long value);
```

## Description

Activates or deactivates the power status globally. Modifying the global power state of the IL is similar to calling [ARILControlSimulationOn](CAPLfunctionARILControlSimulationOn.md) or [ILControlSimulationOff](CAPLfunctionARILControlSimulationOff.md) at all nodes.

## Parameters

- **value**
  - 0: Set power state **off**.
  - 1: Set power state **on**.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

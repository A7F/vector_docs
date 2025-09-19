# ARILControlSimulationOn

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function should not be used in the **on PreStart** event procedure.

## Function Syntax

```plaintext
long ARILControlSimulationOn()
```

## Description

Starts the simulation of the IL. The IL is operational and started. The IL will send PDUs.

## Parameters

—

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

[ARILControlSimulationOff](CAPLfunctionARILControlSimulationOff.md)

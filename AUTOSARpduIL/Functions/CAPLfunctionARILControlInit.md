# ARILControlInit

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILControlInit ()
```

## Description

Initializes the IL. If this function is called in [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md), then the IL will enter the **suspended** state during [on Start](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) and must explicitly be started.

## Parameters

—

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

[ARILControlStart](CAPLfunctionARILControlStart.md) • [ARILControlStop](CAPLfunctionARILControlStop.md)

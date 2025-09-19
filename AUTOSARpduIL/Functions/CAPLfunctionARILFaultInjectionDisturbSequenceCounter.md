# ARILFaultInjectionDisturbSequenceCounter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILFaultInjectionDisturbSequenceCounter(dbMsg dbMessage, long type, long disturbanceMode, long disturbanceCount, long disturbanceValue, long continueMode);
long ARILFaultInjectionDisturbSequenceCounter(dbMsg dbMessage, char signalGroupName[], long type, long disturbanceMode, long disturbanceCount, long disturbanceValue, long continueMode);
```

## Description

Disturbs the SQC or TGL of a PDU or signal group (see [Supported Features](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILFeatures.md)).

The function without the parameter for the signal group will only disturb SQCs or TGLs that are not part of a signal group.

## Parameters

- **dbMessage**: The symbolic name of a PDU in the database.
- **signalGroupName**: The symbolic full name of the signal group.
- **type**:
  - 0: SQC
  - 1: TGL
  - Others: all other values are reserved
- **disturbanceMode**: Defines the function for the disturbance:
  - **0**: Value - Sets the SQC fix to the value of parameter `disturbanceValue`.
  - **1**: Freeze - Current signal value is used (`disturbanceValue` is not used).
  - **2**: Random - Random value is used (`disturbanceValue` is not used).
  - **3**: Offset - Signal value is increased by value of parameter `disturbanceValue`.
- **disturbanceCount**:
  - **-1**: Infinite - Disturbance is continuously applied.
  - **0**: Stop - An active disturbance is stopped and the SQC will be calculated again appropriately.
  - **n > 0**: Count - Do exactly n disturbances.
- **disturbanceValue**: According to the disturbance mode the SQC will optionally be set to this value.
- **continueMode**: Defines the signal value when the disturbance is stopped:
  - **0**: Correct Counter - The counter will continue as if there had never been a disturbance: 0, 1, 2, 6, 6, 5, 6 …
  - **1**: Last Valid Counter - The counter will continue by increasing last valid counter: 0, 1, 2, 6, 6, 3, 4 ...
  - **2**: Last Value - The counter will continue by increasing the last transmitted value: 0, 1, 2, 6, 6, 7, 8 ...

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

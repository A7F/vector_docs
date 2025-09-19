# ARILFaultInjectionDisturbChecksum

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long ARILFaultInjectionDisturbChecksum (dbMsg dbMessage, long type, long disturbanceMode, long disturbanceCount, long disturbanceValue); // form 1`
- `long ARILFaultInjectionDisturbChecksum (dbMsg dbMessage, char signalGroupName[], long type, long disturbanceMode, long disturbanceCount, long disturbanceValue); // form 2`
- `long ARILFaultInjectionDisturbChecksum64 (dbMsg dbMessage, long type, long disturbanceMode, long disturbanceCount, qword disturbanceValue); // form 3`
- `long ARILFaultInjectionDisturbChecksum64 (dbMsg dbMessage, char signalGroupName[], long type, long disturbanceMode, long disturbanceCount, qword disturbanceValue); // form 4`

## Description

Disturbs the CRC of a PDU or signal group (see [CRC Value](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILFeatures.md#CRCValue)). The function without the parameter for the signal group will only disturb CRCs that are not part of a signal group.

Use the ARILFaultInjectionDisturbChecksum64 functions for 64-bit CRC values (e.g., in case of AUTOSAR PROFILE_07).

## Parameters

- **dbMessage**: The symbolic name of a PDU in the database.
- **signalGroupName**: The symbolic full name of the signal group.
- **type**: reserved (should be set to 0).
- **disturbanceMode**: Defines the function for the disturbance:
  - **0**: Value - Sets the CRC fix to the value of parameter `disturbanceValue`.
  - **1**: Freeze - Current signal value is used (`disturbanceValue` is not used).
  - **2**: Random - Random value is used (`disturbanceValue` is not used).
  - **3**: Offset - Signal value is increased by value of parameter `disturbanceValue`.
- **disturbanceCount**:
  - **-1**: Infinite - Disturbance is continuously applied.
  - **0**: Stop - An active disturbance is stopped and the CRC will be calculated again appropriately.
  - **n > 0**: Count - Do exactly n disturbances.
- **disturbanceValue**: According to the disturbance mode the CRC will optionally be set to this value.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

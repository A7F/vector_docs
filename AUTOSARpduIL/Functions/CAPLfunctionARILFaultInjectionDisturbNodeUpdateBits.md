# ARILFaultInjectionDisturbNodeUpdateBits

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILFaultInjectionDisturbNodeUpdateBits (long flags, long disturbanceMode, long disturbanceCount, long disturbanceValue);
```

## Description

Disturbs the Update Bit of all signals and/or signal groups that are sent by the current node (see [Update Bit](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILFeatures.md#UpdateBit)).

## Parameters

- **flags**: Some dedicated bits of the flags parameter determine a specific behavior:
  - **0x3, 0**: Disturbs signal and signal group update bits of node.
  - **0x3, 1**: Disturbs only signal update bits of node.
  - **0x3, 2**: Disturbs only signal group update bits of node.
  - **0x3, 3**: reserved
  - **0xFFFFFFFC, all**: reserved

- **disturbanceMode**: Defines the function for the disturbance:
  - **0, Value**: Sets the update bit fix to the value of parameter **disturbanceValue**.
  - **1, Freeze**: Current signal value is used (**disturbanceValue** is not used).
  - **2, Random**: Random value is used for setting and resetting the update bit (**disturbanceValue** is not used).
  - **3, Opposite**: Signal value is set when update bit should be cleared and is cleared when update bit should be set.
  - **4, Random Set**: The update bit will randomly be not set but will always after transmission be cleared (**disturbanceValue** is not used).
  - **5, Random Reset**: The update bit will always correctly be set but randomly not reset (**disturbanceValue** is not used).

- **disturbanceCount**: 
  - **-1, Infinite**: Disturbance is continuously applied.
  - **0, Stop**: An active disturbance is stopped and the CRC will be calculated again appropriately.
  - **n > 0, Count**: Do exactly n disturbances.

- **disturbanceValue**: According to the disturbance mode the CRC will optionally be set to this value.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

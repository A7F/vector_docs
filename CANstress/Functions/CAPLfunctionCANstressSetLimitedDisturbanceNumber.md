# CANstressSetLimitedDisturbanceNumber

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
void CANstressSetLimitedDisturbanceNumber (dword cycles, dword distPerCycle, dword cyclePause);
```

## Description

Sets the **Limited number of disturbances** disturbance mode. In this mode, the number **n** of disturbances in a disturbance cycle is limited. **n** disturbances will be followed by a configurable pause **p** as long as this is not a single disturbance cycle.

## Parameters

- **cycles**: Defines the number of disturbance cycles. Values from 1 to 65,535 are valid.
- **distPerCycles**: Defines the number of disturbances per disturbance cycle. Values from 1 to 255 are valid.
- **cyclePause**: Defines the length of the pause between two disturbance cycles. The length is defined in ms and may be between 1 and 65,535.

## Return Values

—

## Example

—

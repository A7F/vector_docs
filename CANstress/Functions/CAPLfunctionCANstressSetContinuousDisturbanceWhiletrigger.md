# CANstressSetContinuousDisturbanceWhileTrigger

[CAPL Functions](../../CAPLfunctions.md) » [CANstresss](../CAPLfunctionsCANstressOverview.md) » CANstressSetContinuousDisturbanceWhileTrigger

**Valid for**: CANoe DE

## Function Syntax

```plaintext
void CANstressSetContinuousDisturbanceWhileTrigger (dword type);
```

## Description

Sets the **Continuous disturbance (while trigger)** mode. The continuous disturbance will prevail for as long as the trigger is active. Please note that this mode is generally only useful in conjunction with a software trigger.

## Parameters

- **type**: Defines the type of continuous disturbance. The disturbance can be associated with dominant or recessive bits or it can be an analog disturbance. 2 indicates a dominant disturbance, 3 a recessive disturbance and 4 an analog disturbance (only in conjunction with CANstress DR).

## Return Values

—

## Example

—
